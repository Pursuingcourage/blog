# Hexo使用攻略-添加分类及标签

### 1、**设置菜单** 

​       菜单配置包括三个部分，第一是菜单项（名称和链接），第二是菜单项的显示文本，第三是菜单项对应的图标。       NexT 使用的是 [Font Awesome](http://fontawesome.io/) 提供的图标，       Font Awesome 提供了 600+ 的图标，可以满足绝大的多数的场景，同时无须担心在 Retina 屏幕下       图标模糊的问题。     

编辑 主题配置文件，修改以下内容：

1. 设定菜单内容，对应的字段是 `menu`。           菜单内容的设置格式是：`item name: link`。其中 ` item name `           是一个名称，这个名称并不直接显示在页面上，她将用于匹配图标以及翻译。         

   菜单示例配置

   ```
   menu:
     home: /
     archives: /archives
     #about: /about
     #categories: /categories
     tags: /tags
     #commonweal: /404.html
   ```

   若你的站点运行在子目录中，请将链接前缀的 `/` 去掉

   NexT 默认的菜单项有（标注  的项表示需要手动创建这个页面）：

   | 键值       | 设定值                    | 显示文本（简体中文） |
   | ---------- | ------------------------- | -------------------- |
   | home       | `home: /`                 | 主页                 |
   | archives   | `archives: /archives`     | 归档页               |
   | categories | `categories: /categories` | 分类页               |
   | tags       | `tags: /tags`             | 标签页               |
   | about      | `about: /about`           | 关于页面             |
   | commonweal | `commonweal: /404.html`   | 公益 404             |

2. 设置菜单项的显示文本。在第一步中设置的菜单的名称并不直接用于界面上的展示。Hexo 在生成的时候将使用           这个名称查找对应的语言翻译，并提取显示文本。这些翻译文本放置在 NexT 主题目录下的           `languages/{language}.yml` （`{language}` 为你所使用的语言）。         

   ​           以简体中文为例，若你需要添加一个菜单项，比如 `something`。那么就需要修改简体中文对应的翻译文件           `languages/zh-Hans.yml`，在 `menu` 字段下添加一项：         

   ```
   menu:
     home: 首页
     archives: 归档
     categories: 分类
     tags: 标签
     about: 关于
     search: 搜索
     commonweal: 公益404
     something: 有料
   ```

3. 设定菜单项的图标，对应的字段是 `menu_icons`。此设定格式是 `item name: icon name`，其中 `item name`  与上一步所配置的菜单名字对应，`icon name` 是 Font Awesome 图标的           名字。而 `enable` 可用于控制是否显示图标，你可以设置成 `false` 来去掉图标。         

   菜单图标配置示例

   ```
   menu_icons:
     enable: true
     # Icon Mapping.
     home: home
     about: user
     categories: th
     tags: tags
     archives: archive
     commonweal: heartbeat
   ```

   ​           在菜单图标开启的情况下，如果菜单项与菜单未匹配（没有设置或者无效的 Font Awesome 图标名字）           的情况下，NexT 将会使用  作为图标。         

    请注意键值（如 `home`）的大小写要严格匹配 

   ### 2、创建“分类”选项

   #### 2.1 生成“分类”页并添加tpye属性

   打开命令行，进入博客所在文件夹。执行命令

   ```
   $ hexo new page categories
   ```

   成功后会提示：

   ```
   INFO  Created: ~/Documents/blog/source/categories/index.md
   ```

   根据上面的路径，找到`index.md`这个文件，打开后默认内容是这样的：

   ```
   ---
   title: categories
   date: 2018-06-27 13:47:40
   ---
   ```

   添加`type: "categories"`到内容中，添加后是这样的：

   ```
   ---
   title: categories
   date: 2018-06-27 13:47:40
   type: "categories"
   ---
   ```

   保存并关闭文件。

   #### 2.2 给文章添加“categories”属性

   打开需要添加分类的文章，为其添加categories属性。下方的`categories: xx`表示添加这篇文章到“xx”这个分类。注意：hexo一篇文章只能属于一个分类，也就是说如果在“- xx”下方添加“-xxx”，hexo不会产生两个分类，而是把分类嵌套（即该文章属于 “- xx”下的 “-xxx ”分类）。

   ```
   ---
   title: hello
   date: 2018-05-26 12:12:57
   categories: 
   - xx
   ---
   ```

   至此，成功给文章添加分类，点击首页的“分类”可以看到该分类下的所有文章。当然，只有添加了`categories: xxx`的文章才会被收录到首页的“分类”中。

   ### 3、创建“标签”选项

   #### 3.1 生成“标签”页并添加tpye属性

   打开命令行，进入博客所在文件夹。执行命令

   ```
   $ hexo new page tags
   ```

   成功后会提示：

   ```
   INFO  Created: ~/Documents/blog/source/tags/index.md
   ```

   根据上面的路径，找到`index.md`这个文件，打开后默认内容是这样的：

   ```
   ---
   title: 标签
   date: 2018-05-27 14:22:08
   ---
   ```

   添加`type: "tags"`到内容中，添加后是这样的：

   ```
   ---
   title: 文章分类
   date: 2018-05-27 13:47:40
   type: "tags"
   ---
   ```

   保存并关闭文件。

   #### 3.2 给文章添加“tags”属性

   打开需要添加标签的文章，为其添加tags属性。`tags:`下方的就是这篇文章的标签了

   ```
   ---
   title: hello
   date: 2018-05-26 12:12:57
   categories: 
   - xx
   tags:
   - 
   ---
   ```

   至此，成功给文章添加分类，点击首页的“标签”可以看到该标签下的所有文章。当然，只有添加了`tags: xxx`的文章才会被收录到首页的“标签”中。

   细心的朋友可能已经发现，这两个的设置几乎一模一样！是的，没错，思路都是一样的。所以我们可以打开scaffolds/post.md文件，在tages:上面加入categories:,保存后，之后执行`hexo new 文章名`命令生成的文件，页面里就有`categories:`项了。

   scaffolds目录下，是新建页面的模板，执行新建命令时，是根据这里的模板页来完成的，所以可以在这里根据你自己的需求添加一些默认值。

    

    

    

    

    