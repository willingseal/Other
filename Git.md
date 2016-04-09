#git


***


### git cherry-pick


（从work分支上取出一个commit 或是多个添加到release_1_8_2分支上作为一个新的commit不过commit信息和work分支上的commit信息样，hash值不一样）支持批量添加commit

适用情况：平时我们都在develop分支上进行开发，当需要发布一个版本1.8.2我们需要create一个分支release_1_8_2，develop上进行下一个版本的开发，release_1_8_2分支进行这个版本bug的修改。

这个时候为在work分支上工作，把一个bug修改好了，及时的提交到release_1_8_2分支，继续修改bug或者开发下一个版本功能的工作，最后把今天所有修改的bug和开发下一个版本功能的commit 全部提交到develop上。

也可以在release_1_8_2修改bug，最后把release_1_8_2修改bug的所有commit 添加提交到develop上。原则上所有release_1_8_2有的commit，develop也应该保障有。

➜  iOS-Daenerys git:(develop) git branch -a 所有的分支
➜  iOS-Daenerys git:(develop) git branch -r  远程的分支

➜  iOS-Daenerys git:(develop) git fetch serious release_1_8_2  获取取一个远程分支
➜  iOS-Daenerys git:(develop) git checkout release_1_8_2
➜  iOS-Daenerys git:(release_1_8_2) git branch -a
➜  iOS-Daenerys git:(release_1_8_2) git log --oneline
➜  iOS-Daenerys git:(release_1_8_2) git cherry-pick ad5a2ab    ad5a2ab这个commit为work分支上的一个commit
➜  iOS-Daenerys git:(release_1_8_2) git log --oneline
➜  iOS-Daenerys git:(release_1_8_2) git pull --rebase serious release_1_8_2
➜  iOS-Daenerys git:(release_1_8_2) git push origin release_1_8_2

然后在Github上面自己的origin New pull request 分别去create对应的两个分支的request


***







