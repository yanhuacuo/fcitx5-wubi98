
## 两种选择

fcitx5 原生支持自有二进制码表，以实现一些形码方案的挂入。另外，fcitx5 还支持『中州韵引擎』，即 fcitx5-rime，借助它可以实现更丰富的码表功能。

于是我们有：

- fcitx5 原生码表
- fcitx5-rime

你可以到 [github](https://github.com/yanhuacuo/fcitx5-issues) 上下载这两份配置文件或直接从 [98五笔资源库网盘](http://98wb.ys168.com/) 获取。

### fcitx5 原生码表

如果你的发行版（ 比如 debian11 ) 已官方内置了 fcitx5 框架，那么仅需将配置文件放入即可。

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/01.png)

解压后，给予 `set.sh` 脚本执行权限并执行：

```
sudo chmod 777 set.sh
sh set.sh
```

典型的配置步骤分享：

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/02.png)

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/03.png)

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/04.png)

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/05.png)



### fcitx5-rime

你需要安装一下『fcitx5-rime』这个包，装好之后，才可进行如下操作

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/06.png)

- 字体支持

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/07.png)

- 安放 rime 配置

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/08.png)

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/09.png)

![pic](https://github.com/yanhuacuo/fcitx5-issues/raw/main/1108/10.png)

在添加成功『中州韵』后，可以使用如下功能：

- ctr + ~ = 方案切换
- ctrl + shift + F = 繁简转换
- ctrl + shift + H = 拆分显隐
- ctrl + shfit + J = 三重注解
- z 键 引导「临时拼音」
- z 键 兼有「提示上屏历史」
- ` 键 引导「精准造词」
- ~ 键 引导「以形查音」

另外，『扩展码表』亦支持无码加词：~/.local/share/fcitx5/rime/wubi98_ci.extended.dict.yaml

## 补充

当前这份 fcitx5-rime 是基于我们过去的 opencc 滤镜配置实现的，之所以没有使用更强大的 lua 配置，是因为像 debian 官方仓库的这些打包人员，对 rime 所知甚少，在源码打包时，没有添加 [lua](https://github.com/hchunhui/librime-lua) 与 [charcode](https://github.com/rime/librime-charcode) 两个 librime 的「插件」。

仅当上述两份插件的源码放在 [librime/plugins](https://github.com/rime/librime/tree/master/plugins) 下编译时，才可使用更完整、更强大的 [满血配置](https://github.com/yanhuacuo/fcitx5-issues/blob/main/fcitx5-rime-with-lua.tar.gz)
