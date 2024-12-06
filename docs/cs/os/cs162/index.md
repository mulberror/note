---
title: "CS162: Operating System"
---

## 调试

CS162 的课程中，非常提倡使用 GDB 进行调试，如果一开始使用不是很熟练，使用 `stderr` 输出错误信息。

```c
#define eprintf(fmt, ...) fprintf(stderr, "Error at line %d: ", fmt, __LINE__, __VA_ARGS__)
```

## 环境配置

Docker Destop 中打开将 Container 和 Images 运行起来后，使用以下命令行进行 docker 的开启。

```bash
❯ sudo docker-compose up -d
Password:
WARN[0000] /Users/mulberry/workspace/cs-learning/CS162/cs162-workspace/docker-compose.yml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion 
[+] Running 2/2
 ✔ Network cs162-workspace_default    Created                                                                                                                                                  0.0s 
 ✔ Container cs162-workspace-cs162-1  Started 
```

![alt text](image.png)

```bash
workspace@85831f7574ac [14:32:52] group $ git pull group0 main
From github.com:mulberror/cs162-group0
 * branch            main       -> FETCH_HEAD
fatal: refusing to merge unrelated histories
```

```bash
workspace@85831f7574ac [14:36:08] group $ git pull group0  main --allow-unrelated-histories
From github.com:mulberror/cs162-group0
 * branch            main       -> FETCH_HEAD
Auto-merging .gitignore
CONFLICT (add/add): Merge conflict in .gitignore
Auto-merging README.md
Automatic merge failed; fix conflicts and then commit the result.
```
