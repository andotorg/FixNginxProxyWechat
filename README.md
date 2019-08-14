# FixNginxProxyWechat
fix nginx proxy server  dev  wechat public number repeat request code

> 当进行微信开发的时候，后台通过nginx进行反向代理之后，导致微信获取openid的获取code进行两次请求， 经测试苹果手机不会，而安卓手机会
    具体原因这个帖子讲解的非常详细了：https://developers.weixin.qq.com/community/develop/doc/b8f9f09573e92ffb0e23308d54bcdcf7
    现在通过后端根据code请求获取openid，通过ajax调用后端接口，这样避免了两次调用， 上面帖子中提到的加一个参数，加上这个参数安卓还是不起作用
    @author lucas
    @date 2019-8-14 10:04:02
    @since 1.0


### 帖子

微信公众号网页授权时，回调两次？

像这种网页，我获取code时，会收到两个请求：

code虽然都是一样的，但是ip一个是成都的ip，另一个是上海的ip，有时候是天津的ip，sessionId也不一样。

我也碰到这个问题，我用nginx 做了一次代理，然后用apache 做了一次代理，都是两次请求，但是如果不做代理，就没有这个问题？非常无语？不知道老兄现在解决了吗？

我也遇到这个问题，不仅仅是网页授权回调，在微信里面点击菜单或点击聊天消息中的URL都会发出两次请求？请问如何解决？

服务器也是使用Nginx了反向代理。

