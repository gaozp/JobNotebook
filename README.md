# 简介

使用方法：  
1.clone到本地  
2.添加需要的文件夹或者文章  
3.在summary.md中进行添加对应链接  
4.__使用gitbook serve进行预览__  
```
预览生成的html会放在_book目录下，但是我们已经ignore了，所以需要在另外一个gh-page的分支上使用这些内容  
```
5.直接使用sh gitbook.sh "commit-msg" 来进行提交  
```
该脚本会进行 提交，将md文件push到master分支来保存原始文章，将生成的html文件push到gh-pages分支来进行gitbook展示，最后切回到master分支来进行下一次的修改。
```
