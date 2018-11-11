---
title: 给你的网站加一个live2d
categories: 
- web前端
tags:
- Hexo
---

## 1.安装

`sudo npm install --save hexo-helper-live2d`

## 2.现有模型的安装

use `npm install {packagename}` The package name is the folder name in `packages/` We have:

- `live2d-widget-model-chitose`
- `live2d-widget-model-epsilon2_1`
- `live2d-widget-model-gf`
- `live2d-widget-model-haru/01` (use `npm install --save live2d-widget-model-haru`)
- `live2d-widget-model-haru/02` (use `npm install --save live2d-widget-model-haru`)
- `live2d-widget-model-haruto`
- `live2d-widget-model-hibiki`
- `live2d-widget-model-hijiki`
- `live2d-widget-model-izumi`
- `live2d-widget-model-koharu`
- `live2d-widget-model-miku`
- `live2d-widget-model-ni-j`
- `live2d-widget-model-nico`
- `live2d-widget-model-nietzsche`
- `live2d-widget-model-nipsilon`
- `live2d-widget-model-nito`
- `live2d-widget-model-shizuku`
- `live2d-widget-model-tororo`
- `live2d-widget-model-tsumiki`
- `live2d-widget-model-unitychan`
- `live2d-widget-model-wanko`
- `live2d-widget-model-z16`

## 3.在hexo或者主题_config.yml中添加



> ```
> live2d:
>   enable: true
>   scriptFrom: local
>   pluginRootPath: live2dw/
>   pluginJsPath: lib/
>   pluginModelPath: assets/
>   tagMode: false
>   log: false
>   model:
>     use: live2d-widget-model-wanko
>   display:
>     position: right
>     width: 150
>     height: 300
>   mobile:
>     show: true 
> ```
>
>  <!--use: npm-module package name-->
>
>  
>
>  
>
>  
>
>  
>
>  
>
>  

