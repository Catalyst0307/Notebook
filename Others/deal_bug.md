统一格式：  
> 报错形式  
- 输入命令  
- 报错原因  
- 解决方法  

# Index
[git相关](#1)

<p id="1"></p>

### git相关
> fatal: refusing to merge unrelated histories
- git merge origin/main  
- 合并分支没有取得关联  
- git merge `branch name` --allow-unrelated-histories  

> ! [rejected] main -> main (fetch first) error: failed to push some refs to
- git push
- 远程与本地代码不同步
- git pull --> git push  

> 
