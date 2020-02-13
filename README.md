### [静水博客](http://csyanwb.cn) 搭建笔记
--------

* 首先，在Github上创建三个repo： `CS2015YWB.github.io`（存放博客导航页面） `blog`（存放技术日志博客 based on Jekyll）和`life`（存放随笔杂谈博客 based on Hugo）

* 在本地创建三个文件夹，依次存放三个repo对应的本地版本

* 将三个项目分别部署至Github仓库,保证blog和life两个博客页面均可以正常访问

>**CS2015YWB.github.io**
* `git init`
* `git add .`
* `git commit -m "first commit"`
* `git remote add origin git@github.com:CS2015YWB/CS2015YWB.github.io.git`
* `git push -u origin master`
* 后期版本提交不需要`git remote`，执行`git push origin master`即可

***

>**blog**
* `git clone git@github.com:kitian616/jekyll-TeXt-theme.git`
* 将文件复制到`blog`文件夹中
* 修改`Gemfile`，添加`gem "jekyll-text-theme"`
* 修改`_config.yml`，添加` theme: jekyll-text-theme`
* 执行`bundle install`
* 执行`bundle exec jekyll build`，`bundle exec jekyll serve`,查看效果
* `git init`
* `git add .`
* `git commit -m "first commit"`
* `git remote add blog git@github.com:CS2015YWB/blog.git`
* `git push -u blog master`
* 进入`settings`修改`GIthub Pages`为`master branch`
* 后期版本提交不需要`git remote`，执行`git push blog master`即可

***

>**life**
* `git clone https://github.com/laobubu/jekyll-theme-EasyBook.git life`
* 修改`_config.yml`中修改`url`和`baseurl`为`url: "https://CS2015YWB.github.io"`和`baseurl: "/life"`
* `bundle install`
*  执行`bundle exec jekyll build`，`bundle exec jekyll serve`,查看效果
* `git init`【千万不要忘记重新初始化！！！】
* `git add .`
* `git commit -m "first commit"`
* `git remote add life git@github.com:CS2015YWB/life.git`
* `git push -f -u life gh-pages`
* 后期版本提交不需要`git remote`，执行`git push life gh-pages`即可

***

### 重装系统后，重新把文件`clone`至本地，发现blog和life的再执行以上的`push`命令会出现错误
**blog**
```
➜  life git:(gh-pages) git push blog master
fatal: 'blog' does not appear to be a git repository
fatal: 无法读取远程仓库。

请确认您有正确的访问权限并且仓库存在。
```
**life**
```
➜  life git:(gh-pages) git push life gh-pages
fatal: 'life' does not appear to be a git repository
fatal: 无法读取远程仓库。

请确认您有正确的访问权限并且仓库存在。
```
### 修改相应的命令即可正常`push`，如下所示：

**blog**
```
git push origin master
```
**life**
```
git push origin gh-pages
```

-----

### Change for "life"

* Delete "life" 
* Build "note" Based on Hexo 
* Usage:
	`hexo clean`        -->   clean cache & delete old pages
	`hexo g[enerate]`   -->   generate new pages
	`hexo d[eploy]`     -->   deploy to Github




> ### 重新安装了系统，一次很大的改动！

* 博客首页即`index`只需要从GitHub `clone`下来，即可以正常使用，同样使用`git push origin master`进行push

* 想要让博客简洁一些，`pro`为[GitHub官方](github.dev)提供的基于Jekyll的博客系统，可以用来展示Projects、Interests和Thoughts

> **pro（Jekyll）**

* `git clone git@github.com:github/personal-website.git`将项目`clone`至本地
* 将项目中除去版本控制相关的文件复制到`pro`文件夹中，同时在GitHub创建同名Repository
* `bundle install`
* 修改`_config.yml`，添加`respository: CS2015YWB/pro`
* `bundle exec jekyll build`
* `bundle exec jekyll serve`，查看效果
* `git init`
* `git add .`
* `git commit -m "init commit"`
* `git remote add pro git@github.com:CS2015YWB/pro.git`
* `git push -u pro master`
* 进入`settings`修改`GIthub Pages`为`master branch`
* 后期版本提交不需要`git remote`，执行`git push pro master`即可

> **tech（Hugo）**

* `hugo new site tech`，创建站点
* `cd tech`
* `git clone git@github.com:olOwOlo/hugo-theme-even.git themes/even`

* > **重要:** 在主题的 [`exampleSite`](https://github.com/olOwOlo/hugo-theme-even/tree/master/exampleSite) 目录下有一个 [`config.toml`](https://github.com/olOwOlo/hugo-theme-even/blob/master/exampleSite/config.toml) 文件，**将这个 [`config.toml`](https://github.com/olOwOlo/hugo-theme-even/blob/master/exampleSite/config.toml) 文件复制到你的站点目录下**，根据自己的需求更改即可。

* 修改`config.toml`首行`baseURL = "https://cs2015ywb.github.io/tech/"`

* `hugo new post/my-first-post.md` 
* > **注意:** 对于这个主题，你应该使用 **post** 而不是 **posts**
* `hugo server -D`
* `hugo --theme=even --baseUrl="https://cs2015ywb.github.io/tech/"`
* `cd public`
* `git init`
* `git remote add tech git@github.com:CS2015YWB/tech.git`
* `git add -A`
* `git commit -m "init commit"`
* `git push -u tech master`
* 后续修改
	> `hugo server -D`

	> `hugo --theme=even --baseUrl="https://cs2015ywb.github.io/tech/"`

	> `cd public`

	> `git add -A`

	> `git commit -m "xxxx commit"`

* 后期版本修改过源码不需要`git remote`，执行`git push tech master`即可

> **blog（Hexo）**

* `hexo init blog`
* `cd blog`
* `npm install`
* `git clone git@github.com:SumiMakito/hexo-theme-Journal.git themes/hexo-theme-Journal`
* 修改`_config.yml`中为`theme:hexo-theme-Journal`
* `hexo g`，生成website
* `hexo s`，查看效果
* `hexo d`，上传至Github

### Change Log

