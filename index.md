## Welcome to 宾海洋's Pages

整理一下线上和本地仓库的工程都是些什么，包含哪里功能，东西有点多，有时候要找一些写过的内容都找半天。
前面是python的，后面是java的

### py-workspace\HTornado-master

py-workspace\HTornado-master 实际是我的文库喵，是一个py的web应用，用的HTornado-master框架，前端翻版了百度首页，用户输入文库地址，现在还加了sina博客的url，然后可以下载页面的文档，或者文章内容。
![](https://github.com/OceanBBBBbb/OceanBBBBbb.github.io/blob/master/wenkumiao.jpg)  

```
nothing to show
```

### py-workspace\mlexcu

这个应该是github上下载的一个机器学习的demo，关于房价的，还没仔细看，可以跑起来，原版的效果图看得不是很明白，可以改直观一些。
###### 片段展示:
```
# # 绘制数值型数据的直方图
def traw_pic():
    housing.hist(bins=50, figsize=(20, 15))       # bins指定箱子个数
    #                                               # figsize子图大小
    plt.show()

# 调用Scikit-Learn库进行数据分割
def tran_it(housing):
    train_set, test_set = train_test_split(housing, test_size=0.2, random_state=42)
    housing = train_set.copy()
    housing.plot(kind="scatter", x="longitude", y="latitude", alpha=0.1)
    # alpha 设置散点的透明度
    plt.show()
    # 基于房屋价格的**图
    housing.plot(kind="scatter", x="longitude", y="latitude", alpha=0.4,
      s=housing["population"]/100, label="population",
      # 采用人口数量为半径画圆，增加图例说明
      c="median_house_value", cmap=plt.get_cmap("jet"), colorbar=True,
      # 人口数量的圆圈用房屋中位数价格填充，颜色选取默尔的颜色映射
    )
    plt.legend()
    plt.show()

```

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
