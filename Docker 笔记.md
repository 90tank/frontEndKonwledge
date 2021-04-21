# Docker 笔记

##### -v 和 --mount 的不同

```
-v 历史久远， 一时间难以被替换，如果使用-v 或者 -volume 绑定文件夹，若文件夹 在Docker host上不存在， 那么-v 指令会创建这个挂载点， it always created as a directory.
如果你使用 --mount 去绑定挂载点, 如果docker host上该文件夹不存在，dokcer 不会自动创建文件夹，而是生成一个error.
```



