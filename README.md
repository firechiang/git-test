##### git创建 sshkey
```bash
ssh-keygen -t rsa -C "a576416024@qq.com"   # 创建秘钥 <1，首先提示秘钥存储地址，一般使用默认。2，输入密码<git提交代码时密码，最好不输入，否则提交代码时需要密码>。3，确认密码>
clip < ~/.ssh/id_rsa.pub                   # 复制公钥，然后将公钥粘贴到github
ssh -T git@github.com                      # 测试 秘钥是否成功<1,输入yes。2，如果创建秘钥时输入了密码则需要输入密码。>

最后控制台输出：Hi jiangcihuo! You've successfully authenticated, but GitHub does not provide shell access.
如果username显示的你正确的用户名，表示你已经成功设置SSH key，如果你看到“access denied”，则表示拒绝访问，那你就要使用https去访问，而不是SSH。
```

##### git 修改提交方式
```bash
git remote -v                              # 查看git提交方式<https或ssh>
git remote rm origin                       # 移除现有的提交方式
git remote add origin "git地址"            # 添加新的提交方式 <"git地址"如：git@github.com:jiangcihuo/gragas.git>
git push origin master                     # 从新提交一次代码
```

##### git删除本地未提交的更改
```bash
git clean -df
git reset --hard
```
