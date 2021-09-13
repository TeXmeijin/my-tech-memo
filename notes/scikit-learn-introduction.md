---
tags: ML
---

# [WIP]scikit-learn入門

## 目標

- scikit-learnを用いて、MLに関する基本的な操作ができるようになる。データセットは既存のものを用いてもいい
- 次に、データセットを独自で用意するかカスタマイズした上で同様の操作を行えるようになる
- これらの学習を通して、MLの概観について改めて（ある程度エンジニアリングに素養がある人に対して）話せるレベルで理解する
- ついでに英語力も高まるとなおよし

## まずは公式ないし公式を元にしたものから記事収集

- https://scikit-learn.org/stable/getting_started.html
- https://scikit-learn.org/stable/tutorial/index.html
- https://tutorials.chainer.org/ja/09_Introduction_to_Scikit-learn.html
- https://qiita.com/sugulu_Ogawa_ISID/items/e3fc39f2e552f2355209

## 手順

https://www.jetbrains.com/ja-jp/dataspell/

こちらのIDEの早期アクセスを使ってJupyter Notebook上で動かしてみる。早期アクセスが終わったら、VSCを使うか課金する。これらのNotebookはGitHubに置いておく。

## チュートリアル和訳＆コーディング

### https://scikit-learn.org/stable/tutorial/basic/tutorial.html

Machine learning: the problem setting¶
> 機械学習：問題の設定

In general, a learning problem considers a set of n samples of data and then tries to predict properties of unknown data. If each sample is more than a single number and, for instance, a multi-dimensional entry (aka multivariate data), it is said to have several attributes or features.
> 一般的に学習問題は、n個のサンプルデータの集合を考え、未知のデータの特性を予測しようとするものです。各サンプルが単一の数値以上で、例えば多次元の項目（別名：多変量データ）であれば、いくつかの属性や特徴を持っていると言われます。

entryを項目って訳すんですね。multivariate dataという単語は覚えておいて損なさそう。2文目はIf節が長くて訳しにくかったが、SVを意識して読むとわかりやすいかも。1文目はand thenが間にあるので、スムーズに前から訳して良いパターンでした。

Learning problems fall into a few categories:

supervised learning, in which the data comes with additional attributes that we want to predict (Click here to go to the scikit-learn supervised learning page).This problem can be either:

classification: samples belong to two or more classes and we want to learn from already labeled data how to predict the class of unlabeled data. An example of a classification problem would be handwritten digit recognition, in which the aim is to assign each input vector to one of a finite number of discrete categories. Another way to think of classification is as a discrete (as opposed to continuous) form of supervised learning where one has a limited number of categories and for each of the n samples provided, one is to try to label them with the correct category or class.

regression: if the desired output consists of one or more continuous variables, then the task is called regression. An example of a regression problem would be the prediction of the length of a salmon as a function of its age and weight.

unsupervised learning, in which the training data consists of a set of input vectors x without any corresponding target values. The goal in such problems may be to discover groups of similar examples within the data, where it is called clustering, or to determine the distribution of data within the input space, known as density estimation, or to project the data from a high-dimensional space down to two or three dimensions for the purpose of visualization (Click here to go to the Scikit-Learn unsupervised learning page).