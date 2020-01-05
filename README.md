# pythonfinal python2019秋季学期期末项目展示
* 代码github的url  https://github.com/ViolaW/18flask_C
* pythonanywhere URL/云服务器的域名提交 URL http://viola.pythonanywhere.com/ren_pinkunlv?
* 数据传递描述 将数据从后端传送到前端
* 实现数据的python传送到HTML页面交互，共实现了5个图表的跳转
* 包含基本的templates、static、app.py
* 有合适的数据结构嵌套
* 有项目代码在github中的url 以及pythonanywhere的url 包括readme.md的文档url共有3个链接
* 点击图标上方的五个键位，可以跳转到相应的图表
* 在17级师兄提供的数据基础上，与合作的蓝启良同学两个人共同参与每一个部分代码的讨论，协作，并得出最终的结果。
## python档描述
1.安装并导入pandas、pyecharts、cufflinks、plotly等第三方包
2.运用了flask模板以及jinjia2呈现的web页面，从flask呈现模板
3.Flask提供了一个名为render_template的函数，将这个函数增加到从flask模板导入的函数列表中，根据需要调用这个函数，最终显示出Web应用的 HTML表单。安装Flask环境，导入flask和render_template函数，创建Flask对象实例
4.Flask提供了一个内置对象，名为request。我们利用这个对象可以访问所提交的数据。
5.创建url和函数，用url修饰函数，呈现不同的HTML页面
6.request对象包含一个名为form的字典属性，可以访问从浏览器提交的HTML表单数据。
7.通过表单的功能，实现了数据的交互，可以从筛选按钮中选出相应的数据。
### 部分代码展示
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

## 数据交互 截取部分展示
 return render_template('index.html',
                           myechart=tl.render_embed(),
                           text1='''通过贫困率和贫困人口的两张地图对比可得，地图都有类似的点 两张地图颜色分布和变化趋势大致相同，可以得出贫困率跟贫困人口相关。
                            两份数据图的中东地区数据是都偏大的随着年份的增加，变化都不是很大 我们还可以看出随着年份的增加，尽管全球总体贫困率有所下降，尤其是在中国和拉丁美洲的多数地区，但非洲和部分亚洲地区的贫困率仍居高不下。''')
 ## 自定义函数/模块 截取部分展示
 *def index_bar_every_1_tp():
    df = pd.read_csv("./static/data/pinkunrenkou.csv")
    tl = Timeline()
    for i in range(2010, 2018):
        c = (
            Map()
                .add("世界地图",
                     [(city[i], j) for i, j in zip(list(df['Country Name']), list(df['{}年'.format(i)])) if
                      city.get(i, None)],
                     "world")
                .set_series_opts(label_opts=opts.LabelOpts(is_show=False))
                .set_global_opts(
                title_opts=opts.TitleOpts(title="{}各国贫困人口".format(i)),
                visualmap_opts=opts.VisualMapOpts(max_=80),
            )



