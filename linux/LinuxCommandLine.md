# Linux命令行常用命令

命令|使用|描述
-|-|-
file| |
find|
locate| |
head||
tail||
sort||
man||
info||
ls||
tar||
zcat||
iptable||
route||
lsof||
lscpu||
netstat||

## Linux目录结构

```mermaid
graph LR
    q(root) ==>r(bin)
    q(root) ==>r(x)
    q(root) ==>r(w)
    q(root) ==>r(f)    
    style q   fill:#00ff00,fill-opacity:0.1,stroke:#3399FF,stroke-width:2px
    style r fill:#00ff00,fill-opacity:0.1,stroke:#3399FF,stroke-width:2px

```

```mermaid
  
graph TB
    classDef node fill:#FFFF66,stroke:#3399FF,stroke-width:3px
A(Apple)==>B{Boy}
A===C(Cat)
B.->D((Dog))
C==喵==>D
style A fill:#aa2
```

```mermaid
graph LR
classDef node fill:#FFFF66,stroke:#3399FF,stroke-width:3px
 A --ljla--> B
 A == This is the label text ==> B;
id1(Start)-->id2(Stop) 
```
 