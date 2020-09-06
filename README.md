# 相识(Xiangshi)

#### 中文文本相似度计算器
[![Pypi Version](https://img.shields.io/pypi/v/xiangshi?label=Pypi%20Version)](https://img.shields.io/pypi/v/xiangshi)
[![Downloads](https://pepy.tech/badge/xiangshi)](https://pepy.tech/project/xiangshi)
[![Pypi and Github License](https://img.shields.io/pypi/l/xiangshi?label=Pypi%20and%20Github%20License)](https://img.shields.io/github/license/kiwirafe/xiangshi)
[![Language](https://img.shields.io/github/languages/top/kiwirafe/xiangshi)](https://github.com/kiwirafe/xiangshi)

相识是一款专门为中文打造的文本相似度计算器。这是唯一也是最好的中文文本相似度计算器

相识的优势有：
  - 专攻中文文本相似度比较
  - 使用余弦计算和Simhash两种算法
  - 100%Python语言
  - 自动TFIDF过滤
  - 可以单独计算TF和IDF
  - 支持List和File两种类型
  - 支持多个文件相似度比较
  - 高效、迅速
  - 安装容易
  - 100%开源
  - 长期维护和更新

### 下载与安装
Pip安装：
```sh
$ pip3 install xiangshi
```
国内较慢的话可以使用清华镜像：
```sh
$ pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple xiangshi
```

#### 版本2.1.0来了！
  - **版本2.0.0发布时有点匆忙，发布错版本了，请大家赶紧升级之本版本：**
    pip3 install --upgrade xiangshi

  版本2.0.0:
  - 增加Simhash算法
    - Simhash算法适用于大文本分析，建议大于500字使用
    - 使用 - xs.simhash(Input1, Input2)
  - 增加Minhash算法
    - Minhash算法与Simhash类似。
    -  使用 - xs.minhash(Input1, Input2)
  - **请尽快把xs.cal(Input1, Input2)换成xs.cossim(Input1, Input2)**
    - **版本2.1.0将不支持xs.cal(Input1, Input2)**

### 使用方法
#### 计算文本相似度
##### 余弦相似度
```python
import xiangshi as xs
xs.cossim(Input1, Input2)
```
##### Simhash & Minhash 相似度
```python
import xiangshi as xs
# Simhash
xs.simhash(Input1, Input2)
# Minhash
xs.minhash(Input1, Input2)
```
 - 计算文本相似度时自动由TFIDF过滤
 - Input1 - 第一个输入值，可以是文件的地址或是一个列表
 - Input2 - 第二个输入值，可以是文件的地址或是一个列表

##### 计算TF，IDF，TFIDF
```python
import xiangshi as xs
xs.GetTF(Input)
xs.GetIDF(Input)
xs.GetTFIDF（Input)
```
  - Input - 输入值，可以是文件的地址或是一个列表

##### 计算文本相似度的Input类型
目前相识支持两种类型 - 文件和列表
文件：
```
data/
  |_test1.txt
  |_test2.txt
  |_test3 ~ 10.txt
```
列表（功能尚不完善）：
```
data = [
  test1.txt
  test2.txt
  test3 ~ 10.txt
]
```

### 其他链接：
  - English Version of README.md:
  https://github.com/kiwirafe/xiangshi/blob/master/README(Eng).md
  - Pypi: 
  https://pypi.org/project/xiangshi/
  - Github:
  https://gitee.com/kiwirafe/xiangshi
  - 相识极速版(XiangshiFast):
  https://github.com/kiwirafe/xiangshi
  - 下载数量:
  https://pepy.tech/project/xiangshi
  - Gitee(中国开源):
  https://pypi.org/project/XiangshiFast/
  - 清华镜像链接(无实际价值):
  https://pypi.tuna.tsinghua.edu.cn/simple/xiangshi/
  
### 版本历史
  - v0.1.0: 初始版本
    - 只有TFIDF计算
    - 计算量较大
  - v0.1.1: 版本修改
  - v0.1.2: 病毒修复
  - v0.1.3: 细节修改
  - v0.1.4: TF，IDF和TFIDF彻底脱节
  - v0.2.0: Github上Alpha版本
    - 去掉多余的循环
    - 利用Python的库函数
    - 计算时间增加30倍
  - v0.2.1: Pip准备
  - v0.2.2: 病毒修复
  - v0.2.3: Github上正式发布
  - v0.3.0: Pip发布
  - v0.3.1: Pip上增加README
  - v0.3.2: README增加下载和使用说明
  - v0.3.3: Pip上修改，让用户可以直接使用各种函数
  - v1.0.0: 支持文本相似度计算
    - 支持余弦相似度
    - 余弦相似度： 是通过计算两个向量的夹角余弦值来评估他们的相似度
    - 使用 - xs.cossim(Input1, Input2)
  - v1.0.1: 不再使用set，因为使用的话两个文本的顺序就会不同，导致结果差别巨大（第一次是0.1，第二次就是0.9）解决问题的方案就是保持一开始Dict的顺序，这样子计算中就没有随机性了。
  - v1.0.2: 增加Decimal精确计算
  - v1.0.3: 增加StopText，之前缺乏
  - v1.0.4: 函数自动变成Pip函数
  - v1.1.0: 增加dict2file函数
  - v1.2.0:
    - 增加相识极速版，只支持余弦相似度和File类型，但速度增加10%
  - v1.2.1: README更新，更多注释
  - v1.2.2: 取消Decimal计算，与保留区别不大
  - v1.3.0:
    - Gitee(中国版的Github)上发布，让国内用户更加方便的使用
    - 一些余弦，TFIDF的Input变成Class的变量，使调用函数时更加方便
  - v1.3.1: 病毒修复
  - v1.3.2: 支持清华镜像，让国内用户更加方便的下载
  - v1.3.3(v2.0.0 Beta): Github和Gitee上发布v2.0.0 Beta
  - v2.0.0 Beta:
    - 增加Simhash算法
      - Simhash算法适用于大文本分析，建议大于500字使用
      - 使用 - xs.simhash(Input1, Input2)
    - 增加Minhash算法
      - Minhash算法与Simhash类似。
      -  使用 - xs.minhash(Input1, Input2)

### 相识寓意
>与君初**相识**，
犹如故人归。
天涯明月新，
朝暮最相思。

![Xiangshi](https://imgur.com/zoAnNfx.jpg)

### MIT License
Copyright (c) [2020] [Kiwirafe]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
