## Welcome to 宾海洋's Pages

整理一下线上和本地仓库的工程都是些什么，包含哪里功能，东西有点多，有时候要找一些写过的内容都找半天。
前面是python的，后面是java的


### py\HTornado-master

py\HTornado-master 实际是我的文库喵，是一个py的web应用，用的HTornado-master框架，前端翻版了百度首页，用户输入文库地址，现在还加了sina博客的url，然后可以下载页面的文档，或者文章内容。
![](https://github.com/OceanBBBBbb/OceanBBBBbb.github.io/blob/master/wenkumiao.jpg)  

```
nothing to show
```


### py\mlexcu

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


### py\pc-28

这个厉害了，自己写的自动下单pc蛋蛋幸运28的程序，通过一定的交易策略，实现自动下注，从无到有盈利几百块后就被系统警告冻结了。非常好使，就是会封号。
虽然自动下单会被封，但是爬取数据后做大数据分析或许可以给手动下单提供一些参考。
###### 片段展示:
```
avg_times= 100# 理论上的平均值 86*3/10
def forecast():
    array_full = deal_data() #拿到数据
    may_num = []
    may_i=0
    array_full_i=0
    for value in array_full:
        if(value<=avg_times*0.618):
            may_num.insert(may_i,array_full_i)
            may_i+=1
        array_full_i+=1
    print("本期可能的数字：")
    print(may_num)
    return may_num
```


### py\quant4stock

股票量化交易的工程，里面只有简单的追涨杀跌的一个策略，还有富途牛牛的API都在里面，可以直接往里面加策略。
github上同名的是这个。


### py\sentiment-analysis

下载来的一个文本情感分析的项目。只用了jieba库的文本情绪分析，可以分析txt/excel等文件内容的情感。但是这个应该准确度不高吧，里面用了多线程等内容可以看看。
###### 片段展示:
```
def __analyse_clause(self, the_clause, runout_filepath, print_show):
        sub_clause = {"score": 0, "positive": [], "negative": [], "conjunction": [], "punctuation": [], "pattern": []}
        seg_result = posseg.lcut(the_clause)

        # 将分句及分词结果写进运行输出文件，以便复查
        if runout_filepath is not None:
            self.__write_runout_file(runout_filepath, the_clause + '\n')
            self.__write_runout_file(runout_filepath, str(seg_result) + '\n')
        if print_show:
            print(the_clause)
            print(seg_result)
```


### py\sentimentanalysis-master

git上下载的项目。这个是含机器学习的文本分析，很多地方跑不起来的，只能学习和使用一些片段。


### py\textrank-analy-commonts

这个是自己写的文本分析，里面内容已经比较杂了。
有pkuseg、jieba、word_cloud、textrank4zh、sklearn等内容，云图的练习，爬取豆瓣监督学习的那个代码就出自这个工程。
###### 片段展示:
```
def proc_text(text):
    # 分词
    raw_words = jieba.cut(text, cut_all=True)
    # 词形归一化
    wordnet_lematizer = WordNetLemmatizer()
    words = [wordnet_lematizer.lemmatize(raw_word) for raw_word in raw_words]
    # True 表示该词在文本中，为了使用nltk中的分类器
    return {word: True for word in words}
```

### py\venv

这里面也是一个内容比较多的工程，为公司做的爬虫的代码主要都在这里面。
还有一个开发安卓app的demo。
###### 片段展示:
```
def get_db_url():
    results = db_fob.get_all()
    for row in results:
        try:
            time.sleep(1)
            id = str(row[0])  #
            qq = str(row[1])
            # if(not qq.__contains__('未填写')):
            #     youjian_img.get_img(qq,'qq_'+id)
            email = str(row[2])
            if(not email.__contains__('未填写')):
                youjian_img.get_img(email,'email_'+id)
        except Exception as e:
            print(str(e))
            pass
get_db_url()
```

### py\wechat-article
这里是第一个爬取微信公众号文章的爬虫程序，有通过搜狗搜索的，有公众号后台爬取的，后面加了网页转pdf(也就是为了转爬取的结果)，再后面遇到了验证码问题，这里还有PIL和图像识别的代码。
还有一个爬虫美股invest的代码（有点儿乱）

### py\wechat-article2
这个是提炼了上个版本的爬微信文章的内容，完善了验证码破解，这里又有一个爬虫获取非小号数据的（周末整理一下把爬虫的抽取到一起）。
还有一个比较厉害的auto_article、这个是爬取雅虎新闻调用百度翻译后，自己生产文章，并自动发布到我的头条号的!
文章效果：https://www.toutiao.com/i6646546958032830983/


### py\weiboanalysis
网上的一个svm技术分析新浪微博情感分析的demo.


