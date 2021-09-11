# ts-parcel-template

Ts 自动更新，自动保存，自动打包，模板

### 初始化步骤

1. npm init -y
2. 安装 typescript
   yarn add typescript -D
3. 生成 tsconfig.json
   tsc -init
4. 修改 tsconfig.json 中的配置
   "outDir": "./dist" -- outDir 是 ts 编译后生成 js 文件保存的目录
   "rootDir":"./src" -- rootDir 是自己编写的 ts 源文件所在的目录

   注意：dist src package.json 必须在一个目录下

5. 编译 src 目录以及子目录下的 ts 文件
   tsc - 在 src 当前目录下：输出 tsc -> 会将 src 目录以及子目录的 ts 文件全部编译成 js 文件，并全部输出到 dist 目录中

6. 安装 ts-node -让 node 能直接运行 ts 代码，无须使用 tsc 将代码编译成 js
   yarn add ts-node -D 全部本地都可以

7. 安装 nodemon yarn add nodemon -D
8. 在 package.json 中配置自动检测，自动重启应用程序

* nodemon --watch src/ 检测src目录
* -e ts 表示nodemon命令准备将要监听的是ts后缀的文件
* --exec ts-node ./src/index.ts 表示检测到src目录下有任何变化，都要重新执行index.ts文件

```js
  "scripts": {
    "dev": "nodemon --watch src/ -e ts --exec ts-node ./src/index.ts"
  }
```

9.Parcel打包支持浏览器运行的ts文件,并配置启动脚本
  安装 yarn add parcel-bundler -D