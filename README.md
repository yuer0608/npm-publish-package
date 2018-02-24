# npm-publish-package
publish npm package

### 在npm上注册一个账号

### 选择一个文件夹，然后用命令行到该文件夹下执行 
```bash
npm init
```

  接下来就是一长串表单：

  name：填写你这个包的名字，默认是你这个文件夹的名字。不过这里要着重说一下，最好先去npm上找一下有没有同名的包。最好的测试方式就是，在命令行里面输入npm install 你要取的名字，如果报错，那么很好，npm上没有跟你同名的包，你可以放心大胆地把包发布出去。如果成功下载下来了则不能用该名称

  version：你这个包的版本，默认是1.0.0

  description：其实我也不知道是什么，按回车就好了。。。，这个用一句话描述你的包是干嘛用的，比如我就直接：‘a plugin for express.register routes                base on file path’

  entry point：入口文件，默认是Index.js，你也可以自己填写你自己的文件名

  test command：测试命令，这个直接回车就好了，因为目前还不需要这个。

  git repository：这个是git仓库地址，如果你的包是先放到github上或者其他git仓库里，这时候你的文件夹里面会存在一个隐藏的.git目录，npm会读到这个目录                  作为这一项的默认值。如果没有的话，直接回车继续。

  keyword：这个是一个重点，这个关系到有多少人会搜到你的npm包。尽量使用贴切的关键字作为这个包的索引。我这个包嘛，第一是在express下工作的，然后又是一           个插件plugin，然后又是一个注册路由route用的，而这个路由又是基于文件目录dir，所以很好就得出我的包的索引关键字。

  author：写你的账号或者你的github账号吧

  license：这个直接回车，开源文件来着。。。

  然后它就会问你Are you ok?
  回车Ok！
  然后我们回到我们的文件目录里面去看一看，发现多出来一个package.json文件，点进去基本上就是你刚刚输入的信息。
  
  然后把test文件夹里面的文件放进去，只要把lib文件夹里面的min.js文件替换为你要发布的sdk就行了
  
  ### 登录你的npm账号 输入username password email
  ```bash
  npm login
  ```
  
  如果下方显示 login in as charten on https://registry.npmjs.org/. 则登录成功

  ### 在该目录文件下执行
  
  ```bash
  npm publish
  ```
  
  一般情况下，一旦你要修改你已经发布后的代码，然后又要执行发布操作，务必到package.json里面，把version改一下，比如从1.0.0改为1.0.1，然后在执行     npm publish，这样就可以成功发布了。、
  
  发布成功后npm install 你发布出去的包的名字，然后看看命令行里面是不是把你的包下载了下来。如果下载成功，就说明你的包已经成功地发布在npm上了


