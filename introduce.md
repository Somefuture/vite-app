# vite-app & vue3.0 体验指南

## 直接生成一个vite-app

  `npm init vite-app <project-name>`非常的轻松，没发现什么问题

## eslint

  强迫症表示，没有eslint真的写不了代码。但是init生成的项目并没有相关的配置。既然这样，那只能自己来了。

  1. 搜索 eslint npm，然后cv！
  2. 执行`npm install eslint --save-dev`
  3. 执行`./node_modules/.bin/eslint --init`

      然后一系列的选择，例如运行环境、你的app类别、是否使用ts之类的，跑完的时候成功的报错了。报错如下
      > An error occurred while generating your JavaScript config file. A config file was still generated, but the config file itself may not follow your linting rules.Error: Failed to load plugin 'vue' declared in 'BaseConfig': createRequire is not a function

      翻译如下：
      >生成JavaScript配置文件时发生错误。仍然会生成一个配置文件，但是该配置文件本身可能不遵循您的整理规则。错误：无法加载在“BaseConfig”中声明的插件“vue”：createRequire不是函数
      ps: google 翻译感觉好强啊

      一番折腾，升级了node版本，然后很快又有了新的报错
      >Failed to load plugin '@typescript-eslint' declared in '.eslintrc.js': Cannot find module 'typescript'

  4. 真是一团糟，发现vue3有专门的eslint配置文档，所以决定删除相关文件，重新配置。感觉是个伤心的故事呢。

  5. 删完了，开始！文档地址：[eslint-vue](https://eslint.vuejs.org/user-guide/#installation)

  6. 使用npm下载，执行`npm install --save-dev eslint eslint-plugin-vue@next`

  7. 本地创建一个.eslintrc.js 配置文件,如下

      ```js
      module.exports = {
        extends: [
          // 放置通用规则
          'plugin:vue/vue3-recommended'
        ],
        rules: {} // 设置特色规则，可以覆盖通用规则
      }
      ```
  
  8. 增加eslint规则到.eslintrc.js文件中
  