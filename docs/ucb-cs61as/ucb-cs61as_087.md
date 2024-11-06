# 多重超类

## 多重超类

一个类可以有多个父类是可能的。我们可以有一个`TA`类，一个`singer`类和一个`TA-singer`类。

```
(define-class (singer)
    (method (introduce) '(I am aiming for MTV awards!))
    (method (sing) '(tralala lalala)))

(define-class (TA)
    (method (introduce) '(GO BEARS!))
    (method (teach) '(Let me help you with that box-and-pointer diagram)) )

(define-class (singer-TA)
    (parent (singer) (TA)) )

(define-class (TA-singer)
    (parent (TA) (singer)) )

> (define rohin (instantiate singer-TA))
> (define mona (instantiate TA-singer))

> (ask rohin 'introduce)
(I am aiming for MTV awards!)

> (ask rohin 'sing)
(tralala lalala)

> (ask rohin 'teach)
(Let me help you with that box-and-pointer diagram)

> (ask mona 'introduce)
(GO BEARS!)

> (ask mona 'sing)
(tralala lalala)

> (ask mona 'teach)
(Let me help you with that box-and-pointer diagram) 
```

请注意，`TA-singer`和`singer-TA`都继承了`TA`类和`singer`类，但顺序不同。当我们向这两个类的实例发送相同的消息时，第一个父类优先。

## 测验备忘单

在测验中，除了你通常拥有的单面双面备忘单之外，你可能还需要一份[这份备忘单](https://docs.google.com/file/d/0B2F__e2jC6gQSHhBdERPZ0pVRG8/edit?usp=drive_web)。
