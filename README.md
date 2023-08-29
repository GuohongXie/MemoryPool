# MemoryPool

参考Nginx实现的一个简易的memory_pool, 更好管理小块内存空间，减少内存碎片。

## 开发环境

- 操作系统：`Ubuntu 20.04 LTS`
- 编译器：`clang++ 10.0.0-4ubuntu1`
- 编辑器：`vscode`
- 版本控制：`git`
- 项目构建：`cmake 3.16.3`


## 构建项目
项目依赖
- `cmake`

下载项目

```shell
git clone git@github.com:GuohongXie/MemoryPool.git
```

执行脚本构建项目

```shell
cd ./MemoryPool && bash build.sh
```