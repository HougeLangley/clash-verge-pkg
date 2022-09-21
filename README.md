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
