# ubuntu 14.04 中如何安装 node v4 ？


```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.27.1/install.sh | bash
```

退出 shell 重新登录，执行

```
nvm ls-remote

```

可以看到最近的 node 版本是 4.1.1 ，执行安装

```
nvm install 4.1.1
```

这样会报警告

···
nvm is not compatible with the npm config "prefix" option: currently set to "/home/peter/.npm-global"
Run `npm config delete prefix` or `nvm use --delete-prefix v4.1.1` to unset it.
···

这是由于咱们自己做的 prefix 造成的。解决方法

```
mv .npmrc npmrc
nvm install 4.1.1
mv .npmrc npmrc
```

这样

```
node -v
```

可以看到系统上的 node 版本已经是 4.1.1 了。
