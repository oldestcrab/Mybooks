### vscode中的插件Settings Sync（设置和插件同步）基本用法

1. vscode搜索并安装插件Settings Sync
2. 登陆`Github>Your profile>settings>Developer settings>personal access tokens>generate new token`，输入名称，勾选Gist，提交,保存`Github Access Token`
2. 打开vscode，快捷键 `shift+alt+u` 或 `ctrl+p` 输入`>sync`点击`update/updload settings`输入Token，上传成功后会返回`Gist ID`，保存此`Gist ID`. 
3. 在需要同步的电脑打开VSCode,安装相同的插件
4. 按快捷键 `shift+alt+d` 或 `ctrl+p` 输入`>sync`点击`Download Settings`
5. 把`GITHUB GIST`的内容粘贴然后回车
6. 等待下载同步内容
7. 之后两台电脑间同步只要按下快捷键`shift+alt+d`即可（记得修改了设置要上传`shift+alt+u` ）
 

### 常见错误

##### Sync : Invalid / Expired GitHub Token. Please generate new token with scopes mentioned in readme. Exception Logged in Console.


> 这个问题大部分是由于gist id的访问令牌token失效了，只需要重新生成一下gist id的token并保存在配置文件里面即可
> 注意：这里重新生成之后，有关此gist id引用到的地方的访问令牌也需要同步更新，否则没办法使用。
> Replace token
> 复制重新生成好的token，修改配置文件
> 
> Win下：C:\Users\Administrator\AppData\Roaming\Code\User
> Mac下：~/Library/Application Support/Code/User/syncLocalSettings.json
> Linux下：~/.config/Code/User/syncLocalSettings.json
> 进入目录后，找到 syncLocalSettings.json 这个文件，查找token，并替换后面复制的值，就可以顺利进行同步配置信息了。