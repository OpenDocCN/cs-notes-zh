# 027：账户与认证

在本节课中，我们将实现完整的Google登录流程，并对前端和后端进行修改以支持登录功能。这是一个内容丰富的实践环节，我们将一步步共同完成。

## 概述

我们将从实现基本的登录/登出按钮开始，然后逐步构建用户数据存储、用户认证、动态用户资料页面，并最终使用React Context来全局管理用户状态，以优化应用性能。

## 6.1：实现前端登录状态

上一节我们了解了工作坊的整体目标，本节中我们来看看如何在前端实现登录状态的跟踪。

首先，我们需要在导航栏组件中创建一个React状态来跟踪用户是否已登录。

在 `navbar.jsx` 文件中，使用 `useState` 钩子创建一个名为 `loggedIn` 的状态，初始值设为 `false`。

```jsx
const [loggedIn, setLoggedIn] = useState(false);
```

现在，当Google登录组件成功返回时，前端应知道用户已登录。它会调用 `handleLogin` 函数。我们需要在这个函数中更新状态。

```jsx
const handleLogin = (response) => {
    console.log(response);
    setLoggedIn(true);
};
```

对于登出功能，Google的库没有提供现成的登出按钮。我们将使用一个普通的按钮组件，并为其定义 `handleLogout` 函数。

以下是需要添加的登出按钮和函数：

```jsx
<button onClick={handleLogout}>Log Out</button>

const handleLogout = () => {
    console.log("Logged out");
    setLoggedIn(false);
};
```

接下来，我们需要根据 `loggedIn` 状态来条件性地渲染登录或登出按钮。

以下是条件渲染的模板：

```jsx
{loggedIn ? (
    <button onClick={handleLogout}>Log Out</button>
) : (
    <GoogleLogin
        onSuccess={handleLogin}
        // ... 其他属性
    />
)}
```

至此，我们实现了根据前端状态显示不同按钮的功能。当用户登录后，应能看到登出按钮；未登录时，则看到登录按钮。

## 6.2：创建用户数据模型

现在用户可以进行登录，让我们来存储使用Catbook的用户数据。思考一下如何实现。

我们将在MongoDB数据库中添加一个用户集合来跟踪所有用户。

正如在数据库课程中介绍的，我们需要在后端定义用户模型和模式。在 `server/models` 文件夹中，新建一个 `user.js` 文件。

你可以从 `story.js` 复制模板，然后修改名称和集合。对于这个模式，我们需要两个字段：`name`（字符串类型）和 `googleId`（字符串类型）。

以下是 `user.js` 文件的内容：

```jsx
const mongoose = require('mongoose');

const UserSchema = new mongoose.Schema({
    name: String,
    googleId: String
});

const UserModel = mongoose.model('user', UserSchema);
module.exports = UserModel;
```

这样，我们就创建了一个遵循该模式的结构化用户集合。

## 6.3：连接前后端认证

上一节我们创建了用户模型，本节中我们来看看如何将前端的登录令牌传递到后端进行验证。

首先，后端已经使用会话来保持认证状态。我们还有一个由Web Lab工作人员编写的 `auth.js` 库，其中提供了 `authLogin` 和 `authLogout` 函数。

*   `authLogin` 函数：接收前端发送的令牌，向Google验证其有效性。如果有效，则为首次登录的用户创建新用户记录，并在会话中设置用户信息。
*   `authLogout` 函数：将 `req.session.user` 设置为 `null`，从而清除会话中的用户信息。

现在，我们需要将前端获取的令牌发送到后端。为此，我们将在服务器上创建两个新的POST端点：`/api/login` 和 `/api/logout`。

在 `api.js` 中添加以下路由：

```jsx
router.post('/login', authLogin);
router.post('/logout', authLogout);
```

接下来，在前端的 `navbar.jsx` 中，修改 `handleLogin` 和 `handleLogout` 函数来调用这些API端点。

在 `handleLogin` 中，从Google的响应中获取令牌，然后将其发送到后端：

```jsx
const handleLogin = async (response) => {
    const userToken = response.credential;
    await post('/api/login', { token: userToken });
    // 后续会更新状态
};
```

在 `handleLogout` 中，只需调用登出端点：

```jsx
const handleLogout = async () => {
    await post('/api/logout');
    // 后续会更新状态
};
```

现在，我们的登录流程就完整了：前端通过Google界面登录，获取令牌，然后通过POST请求将令牌发送到后端进行验证和会话持久化。点击登出则会清除会话中的用户信息。

## 6.4：关联故事和评论与用户

现在我们已经可以登录，但发布故事和评论时仍然显示“匿名用户”。我们希望显示实际登录用户的名称。

我们需要跟踪所有故事和评论的创建者。为此，我们将在故事和评论的模式中添加一个 `creatorId` 字段。

修改 `story.js` 和 `comment.js` 中的模式，添加 `creatorId: String` 字段。

接着，更新 `api.js` 中的POST路由。当创建新故事或评论时，我们不再传递“匿名用户”，而是传递实际用户的名称和ID。

在发布故事的路由中，进行如下修改：

```jsx
const newStory = new StoryModel({
    creator_name: req.user.name, // 使用登录用户的名字
    creator_id: req.user._id,    // 使用登录用户的ID
    content: req.body.content
});
```

对发布评论的路由进行类似的修改。

完成这些更改后，新发布的故事和评论就应该显示发布者的真实姓名了。

## 6.5：实现动态用户资料页

现在，每个故事和评论都显示了用户名。我们希望点击这些名字时，能跳转到相应用户的资料页面。

首先，我们需要创建一个唯一的URL，格式为 `/profile/:userId`。这可以通过在React Router的路径中传递 `userId` 参数来实现。

在 `index.jsx` 中，将个人资料页的路由从静态路径 `/profile` 改为动态路径 `/profile/:userId`。

```jsx
<Route path="/profile/:userId" element={<Profile />} />
```

现在，我们需要在点击故事中的用户名时，导航到 `/profile/creatorId`。`creatorId` 信息来自 `feed.jsx`，它通过API请求从后端获取故事数据，其中包含了新的 `creatorId` 字段。

我们需要将 `creatorId` 作为属性（prop）从 `Feed` 组件传递到 `Card` 组件，再传递到 `SingleStory` 组件。

在 `SingleStory` 组件中，将显示用户名的 `<span>` 标签替换为 `Link` 组件：

```jsx
<Link to={`/profile/${props.creatorId}`}>{props.creator_name}</Link>
```

这样，点击用户名就会跳转到动态生成的用户资料页面。

## 6.6：在资料页获取并显示用户信息

点击链接后，我们进入了用户资料页，但页面显示的名字是错误的。我们需要在资料页组件中获取并显示对应用户的名称。

在 `Profile.jsx` 组件中，我们可以通过 `useParams` 钩子获取URL中的 `userId` 参数。

为了获取用户信息，我们需要在后端创建一个新的API端点。这个端点将接收 `userId`，使用Mongoose查询在数据库中查找对应用户，并将用户信息返回给前端。

在 `api.js` 中添加以下GET端点：

```jsx
router.get('/user', async (req, res) => {
    const user = await UserModel.findById(req.query.userId);
    res.send(user);
});
```

现在，在前端的 `Profile.jsx` 组件中，我们可以使用 `useEffect` 钩子来调用这个API端点，获取用户数据并保存到状态中。

```jsx
const [user, setUser] = useState(null);
const { userId } = useParams();

useEffect(() => {
    const fetchUser = async () => {
        const userData = await get(`/api/user?userId=${userId}`);
        setUser(userData);
    };
    fetchUser();
}, [userId]);
```

为了避免在用户数据加载完成前出现错误，我们可以进行条件渲染：

```jsx
if (!user) {
    return <div>Loading...</div>;
}
return (
    <div>
        <h1>{user.name}'s Profile</h1>
        {/* ... 其他内容 */}
    </div>
);
```

现在，点击用户名就会跳转到显示正确用户名的个人资料页面了。

## 6.7：更新导航栏与登录状态持久化

你可能注意到，导航栏上的“Profile”链接现在失效了，因为我们将其改为了动态路由 `/profile/:userId`。我们希望这个链接能指向当前登录用户的个人资料页。

为此，我们需要在导航栏中维护一个 `userId` 状态，并用它来替换之前的 `loggedIn` 状态。

在 `navbar.jsx` 中，将 `loggedIn` 状态替换为 `userId` 状态，初始值为 `null`。然后更新 `handleLogin` 和 `handleLogout` 函数，分别设置和清除 `userId`。

```jsx
const [userId, setUserId] = useState(null);

const handleLogin = async (response) => {
    const userToken = response.credential;
    const user = await post('/api/login', { token: userToken });
    setUserId(user._id); // 假设后端返回用户对象
};

const handleLogout = async () => {
    await post('/api/logout');
    setUserId(null);
};
```

接着，将导航栏中“Profile”链接的 `to` 属性从 `/profile` 改为 `/profile/${userId}`。

![](img/c9469ad3b181e31124123d6653fbb75a_1.png)

![](img/c9469ad3b181e31124123d6653fbb75a_3.png)

现在，登录后点击导航栏的“Profile”链接，就会跳转到自己的资料页。

但是，如果刷新页面，`userId` 状态会重置，用户会显示为登出状态。这是因为 `userId` 只存储在前端状态中。然而，后端已经在会话中保存了用户信息。

为了解决这个问题，我们需要在导航栏加载时，询问后端当前用户是否仍然登录。我们将在后端创建一个名为 `/api/whoami` 的GET端点。

在 `api.js` 中添加：

```jsx
router.get('/whoami', (req, res) => {
    if (req.user) {
        res.send(req.user);
    } else {
        res.send({});
    }
});
```

然后，在 `navbar.jsx` 的 `useEffect` 钩子中调用这个端点，如果返回用户信息，则设置 `userId` 状态。

```jsx
useEffect(() => {
    const checkLogin = async () => {
        const user = await get('/api/whoami');
        if (user._id) {
            setUserId(user._id);
        }
    };
    checkLogin();
}, []);
```

最后，根据 `userId` 是否存在，条件性地渲染“Profile”链接。

这样，登录状态在页面刷新后也能得以保持。

## 6.8：使用Context优化状态管理

目前，我们在多个组件（如 `Feed`、`CommentsBlock`）中都需要知道用户是否登录，以便决定是否显示发布故事和评论的输入框。如果每个组件都调用 `/api/whoami`，会产生大量不必要的网络请求。

一个更好的解决方案是使用React Context进行全局状态管理。我们将只在应用的根组件（`App`）中调用一次 `/api/whoami`，然后将 `userId` 存储在Context中，所有子组件都可以访问它。

首先，创建一个Context文件，例如 `UserContext.jsx`：

```jsx
import { createContext } from 'react';
export const UserContext = createContext(null);
```

然后，在 `App.jsx` 中：
1.  将 `userId` 状态、`whoami` 请求、`handleLogin` 和 `handleLogout` 函数从 `navbar.jsx` 移动到 `App.jsx`。
2.  将 `handleLogin` 和 `handleLogout` 作为属性传递给 `Navbar` 组件。
3.  使用 `UserContext.Provider` 包裹应用的主要部分，并将 `userId` 作为值提供。

```jsx
<UserContext.Provider value={userId}>
    <Navbar handleLogin={handleLogin} handleLogout={handleLogout} />
    <Outlet />
</UserContext.Provider>
```

在 `Navbar.jsx` 和其他需要 `userId` 的组件（如 `Feed.jsx`、`CommentsBlock.jsx`）中，使用 `useContext` 钩子来消费这个Context值。

```jsx
const userId = useContext(UserContext);
```

现在，我们可以在 `Feed` 和 `CommentsBlock` 中根据 `userId` 是否存在，条件性地渲染输入框组件。

```jsx
{userId && <NewStory />}
{userId && <NewComment />}
```

这样，我们只发起了一次API请求，并通过Context高效地管理了全局用户状态，避免了属性钻取（prop drilling）和重复请求。

## 总结

![](img/c9469ad3b181e31124123d6653fbb75a_5.png)

本节课中，我们一起完成了Catbook应用的账户与认证系统。我们从实现前端登录状态开始，逐步构建了后端用户模型、认证API、动态用户资料页，并最终使用React Context优化了全局状态管理。现在，用户可以使用Google登录，其登录状态得以持久化，发布的内容会关联用户信息，并且界面会根据登录状态动态显示相关功能。