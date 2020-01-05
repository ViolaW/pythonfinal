# pythonfinal python2019秋季学期期末项目展示
* 代码github的url  https://github.com/ViolaW/18flask_C
* pythonanywhere URL/云服务器的域名提交 URL http://viola.pythonanywhere.com/ren_pinkunlv?
* 数据传递描述 将数据从后端传送到前端
* 实现数据的python传送到HTML页面交互，共实现了5个图表的跳转
* 包含基本的templates、static、app.py
* 有合适的数据结构嵌套
* 有项目代码在github中的url 以及pythonanywhere的url 包括readme.md的文档url共有3个链接
* 点击图标上方的五个键位，可以跳转到相应的图表
## python档描述
1.安装并导入pandas、pyecharts、cufflinks、plotly等第三方包
2.运用了flask模板以及jinjia2呈现的web页面，从flask呈现模板
3.Flask提供了一个名为render_template的函数，将这个函数增加到从flask模板导入的函数列表中，根据需要调用这个函数，最终显示出Web应用的 HTML表单。安装Flask环境，导入flask和render_template函数，创建Flask对象实例
4.Flask提供了一个内置对象，名为request。我们利用这个对象可以访问所提交的数据。
5.创建url和函数，用url修饰函数，呈现不同的HTML页面
6.request对象包含一个名为form的字典属性，可以访问从浏览器提交的HTML表单数据。
7.通过表单的功能，实现了数据的交互，可以从筛选按钮中选出相应的数据。
* 部分代码展示
*import plotly as py
import cufflinks as cf
import pandas as pd
from flask import Flask
from pyecharts.charts import Geo
from pyecharts import options as opts
from pyecharts.globals import ChartType, SymbolType, ThemeType
from pyecharts.charts import Bar, Tab, Line, Map, Timeline, Grid, Page
from flask import render_template, request

## Web app档描述
1.后端服务器成功启动：执行 app.py 启动后端服务器，等待web请求。启动成功.

2.接着，服务器访问 弹出网址 ，启动前端web 请求

3.app.py中执行了@app.route('/') 下的 index()函数，产生影响国家贫困率的因素分析的HTML页面

4.紧接着，前端浏览器收到web响应，出现HTML页面

【前端页面——首页】
点击按钮“首页”，即可跳转到(首页);

点击按钮“2010-2017各国贫困率”，即可跳转到(2010-2017各国贫困率);

点击按钮“2010-2017各国贫困人口”，即可跳转到(2010-2017各国贫困人口);

点击按钮“2010-2017各国人均GDP”，即可跳转到(2010-2017各国人均GDP);

点击按钮“2010-2017各国贫困率跟贫困人口的关系”，即可跳转到(2010-2017各国贫困率跟贫困人口的关系).





