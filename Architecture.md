# 项目架构图
```mermaid
flowchart TD
    U["User_Client"]
    B["Backend"]
    S["MeiliSearch"]

    U <--> B
    B <--> S
```

MeiliSearch 负责索引歌曲信息、专辑信息、艺术家信息。