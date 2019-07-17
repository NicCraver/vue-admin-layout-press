# VuePress 使用方法

[项目源码](https://github.com/NicCraver/whihaozhuo)


## 目录结构
```
.
│  README.md                   //首页
│
├─.vuepress                    //vuepress配置文件夹
│  │  config.js                //配置文件夹，配置布局内容等
│  │  enhanceApp.js
│  │
│  ├─components
│  │  │  demo-component.vue
│  │  │  OtherComponent.vue
│  │  │
│  │  └─Foo
│  │          Bar.vue
│  │
│  └─styles
│          index.styl
│          palette.styl
│
├─config
│      README.md               //编写文档的目录
│
└─guide                        //编写文档的目录
        README.md
        using-vue.md
```

## .vuepress下的config.js
``` js
const { description } = require('../../package')

module.exports = {
  title: '武汉好卓大前端组',//左上角标题，浏览器头部title，首页图片下面的加粗文字
  description: "武汉好卓前端开发文档",//描述信息
  head: [
    ['meta', { name: 'theme-color', content: '#3eaf7c' }],
    ['meta', { name: 'apple-mobile-web-app-capable', content: 'yes' }],
    ['meta', { name: 'apple-mobile-web-app-status-bar-style', content: 'black' }]
  ],
  themeConfig: {
    repo: '',
    editLinks: false,
    docsDir: '',
    editLinkText: '',
    lastUpdated: false,
    nav: [//顶部导航栏
      {
        text: 'Guide',//名称
        link: '/guide/',//对应目录
      },
      {
        text: 'Config',
        link: '/config/'
      },
      {
        text: 'VuePress',
        link: 'https://v1.vuepress.vuejs.org'
      }
    ],
    sidebar: //侧边栏
    {
      '/guide/': [
        {
          title: '前端开发文档',
          collapsable: false,
          children: [//对应文件夹中的.md文件名
            '',
            'admin-layout',
            'Vue-Markdown',
            'netlify'
          ]
        }
      ],
    }
  },

  /**
   * Apply plugins，ref：https://v1.vuepress.vuejs.org/zh/plugin/
   */
  plugins: [
    '@vuepress/plugin-back-to-top',
    '@vuepress/plugin-medium-zoom',
  ]
}
```