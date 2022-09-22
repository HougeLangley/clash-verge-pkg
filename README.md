# clash-verge 在 Archlinux 和 Gentoo 上打包

## 介绍 ##

1. clash 在 Linux 平台已经有一些比较方便客户端了，CLI 和 GUI 的都有，个人使用下来，尤其在移动办公和居家使用两种环境切换来看，clash-verge 最为方便；
2. 图形化方便理解，功能多样，集成度高；
3. 作者在持续更新。

## 构建 ##

1. 目前还是利用 yarn 创建的 deb 二次分包后打包 pkg 包
2. archlinux 版本完全在 archlinux 容器下构建；
3. gentoo 版本完全在最新 gentoo 容器下构建。

## 打包的目的 ##

1. 个人使用，测试和反馈
2. 学习，后续如果能够直接打包 pkg 会更好

## Archlinux 安装方式 ##

1. 添加我的个人源：
    - `[xxx]`
    - `SigLevel = Optional TrustAll`
    - `Server = http://hougearch.litterhougelangley.club/x86_64/`
2. 添加后，`pacman -Sy; pacman -S clash-verge-git` 即可。

## Gentoo 安装方法 ##

1. 就像上面构建部分所述，deb 包我在 Gentoo 的 lxd 容器中进行打包，随后修改名称为当前日期后发布到 github release 页面为 Gentoo 后续分发做准备；
2. 目前完成 Gentoo 上的 ebuild 编写，并能将 deb 分发成 pkg 包，安装到 Gentoo 系统中提供给用户使用。

![界面](screenshot/01.png)

![设置](screenshot/02.png)

![可以正常切换内核](screenshot/03.png)

## Gentoo 系统如何参与测试和使用 ##

1. 添加我的测试 overlay
    - `[clash-verge]`
    - `location = /var/db/repos/clash-verge`
    - `sync-type = git`
    - `sync-uri = https://github.com/HougeLangley/clash-verge-bin-overlay.git`
2. 以下命令请在 root 权限下运行
    - `emerge --sync; emerge -avl net-proxy/clash-verge-bin`
3. 等待完成后就能正常使用了，如果各位使用有任何问题，请提交 issue 给我，我会反馈给作者。