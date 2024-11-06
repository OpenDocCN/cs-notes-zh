# 常见错误

## 试一试自己动手！

将以下内容输入到 Racket 解释器中。其中大部分会生成错误。阅读错误信息并尝试理解其含义。这一部分不需要提交任何内容。

```
=> (require berkeley) ;this should not error out. if it does, ask a TA for help
=> (bar 9)
=> (first '())
=> (bf '())
=> (first (bf '(1)))
=> (define (foo x) (+ x 1))) ;notice the extra parenthesis at the end
=> (foo 2 4)
=> (foo)
=> (define baz 3)
=> (baz 8)
=> (se garbly 4)
=> (se 'garbly 4)
=> (se baz 4) 
```

你还应该查看[常见错误列表](https://docs.google.com/document/d/1jGtldEcm_qPoHGknJOkWj1D4-doyBjDivaV_Vn7_Hxk)
