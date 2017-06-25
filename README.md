##1，概述
>在django中，项目的组织结构为一个项目包含多个应用，一个应用对应一个业务模块。

>本案例采用，创建项目的名称为test1，创建应用名称为booktest。

##2，创建项目
第一步：进入自己的项目工作空间：
>在当前用户的某个目录下创建项目，这样不会发生权限问题。

此处在/home/python/pytest/目录下创建项目

```
cd /home/xiaoke/PycharmProjects/DjangoTest
workon py3_space01 # 进入虚拟环境

```
创建项目的命令如下：

```
django-admin startproject 项目名称
例：
django-admin startproject test02
```
![这里写图片描述](http://img.blog.csdn.net/20170625162122429?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxNDc0NTE5NA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

接下来可以使用IDE打开此目录，开发项目了，此处使用pycharm打开DjangoTest目录。
##3，项目默认目录说明
进入test02目录，查看目录数形结构

```
cd  test02 
tree 
```
目录结构如下图：
![这里写图片描述](http://img.blog.csdn.net/20170625162527402?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxNDc0NTE5NA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

+ manage.py是项目运行的入口，指定配置文件路径。
+ 与项目同名的目录，此处为test02，包含项目的配置文件
+ ___init.py是一个空文件，作用是这个目录test02可以被当作包使用。
+ settings.py是项目的整体配置文件。
+ urls.py是项目的URL配置文件。
+ wsgi.py是项目与WSGI兼容的Web服务器入口
##4,创建应用app
使用一个应用开发一个业务模块，此处创建应用名称为fruit。
创建应用的命令如下：
> python manage.py startapp fruit

![这里写图片描述](http://img.blog.csdn.net/20170625165220562?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxNDc0NTE5NA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

+ ___init.py_是一个空文件，表示当前目录fruit可以当作一个python包使用。
+ tests.py文件用于开发测试用例，在实际开发中会有专门的测试人员，这个事情不需要我们来做。
+ models.py文件跟数据库操作相关。
+ views.py文件跟接收浏览器请求，进行处理，返回页面相关。
+ admin.py文件跟网站的后台管理相关。
+ migrations文件夹初始化操作。

##5，安装应用app
应用创建成功后，需要安装才可以使用，也就是建立应用和项目之间的关联，在test02/settings.py中INSTALLED_APPS下添加应用的名称就可以完成安装。

初始项目的INSTALLED_APPS如下图：
![这里写图片描述](http://img.blog.csdn.net/20170625171552772?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxNDc0NTE5NA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

接下来在元组中添加一个新的项，当前示例为fruit

> 'fruit',

![这里写图片描述](http://img.blog.csdn.net/20170625171805672?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxNDc0NTE5NA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

##6,开发服务器

在开发阶段，为了能够快速预览到开发的效果，django提供了一个纯python编写的轻量级web服务器，仅在开发阶段使用。

运行服务器命令如下：

```
python manage.py runserver ip:端口
例：
python manage.py runserver
可以不写IP和端口，默认IP是127.0.0.1，默认端口为8000。
```
服务器成功启动后如下图：
![这里写图片描述](http://img.blog.csdn.net/20170625172044023?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxNDc0NTE5NA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

紧接着在浏览器中输入网址“127.0.0.1:8000”，或者按着ctrl键点击上图中标示出来的地址，可以查看当前站点开发效果。

如果增加、修改、删除文件，服务器会自动重启;
按ctrl+c停止服务器。

![这里写图片描述](http://img.blog.csdn.net/20170625172307650?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxNDc0NTE5NA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

至此，Django入门级项目搭建完成，谢谢！！！

