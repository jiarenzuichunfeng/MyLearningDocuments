会话控制

常见的会话控制技术有三种

cookie

cookie是Http服务器发送到用户浏览器并保存在本地的一小块数据

cookie的特点

浏览器向服务器发送请求时，会自动将当前域名下可用的cookie设置在请求头中，然后传递给服务器

express 设置cookie

res.cookie(’建‘，’值‘，{maxAge：数字毫秒（设置过期时间）})  会在浏览器关闭的时候，销毁

express 删除cookie

res.clearCookie(’’要删除的cookie名)

express 读取cookie

安装 cookie-parser

session

session 是保存在服务器端的一块数据，保存当前访问用户的关键信息

express 操作session

安装 express-session  对session进行操作   connect-mongo

token

token是服务端生成并返回给http客户端的一串加密字符串，token中保存着用户信息

token的特点

服务端压力小

相对安全

扩展性更强

JWT

JWT是目前最流行的跨域认证解决方案，可用于基于token的身份验证

JWT使token的生成与校验更规范

我们可以使用jsonwebtoken 包来操作token