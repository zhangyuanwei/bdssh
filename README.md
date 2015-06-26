# bdssh
Baidu ssh

方便百度内部登录的脚本


## 使用方式

修改脚本中第二行和第三行的用户名和密码。  
用户名就是你的邮箱用户名，密码是你每次 token 之前输入的那个 pin 码。  
出现Enter SecurID 的时候，输入当前的 token 码。  

还能自动输入开发机器密码哦，只需要加 -P 参数，例如：  
`bdssh rd@xxxxxxxx.vm.baidu.com -P MhxzKhl`

配合 alias 更好用  
```
alias ssh-xxxx='bdssh rd@xxxxxxxx.vm.baidu.com -P MhxzKhl'
ssh-xxxx
```

然后把脚本添加到 PATH 路径下。  
然后 `bdssh zhangyuanwei@cp01-rdqa-dev376.cp01.baidu.com` 就行了  


如果要用 rz sz 传文件的话，安装 zssh ，并把脚本 14 行的 `spawn ssh "$username@$server"` 替换为 `spawn zssh "$username@$server"`,   
zssh 的具体用法请参考 http://linux.die.net/man/1/zssh
