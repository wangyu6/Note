# hello markdown
[toc]
## what can i do for you

name|name should be long|np
-|-|-
tom|bob|alice

*andwhatis*`

~~right~~

~~maybe~~
*so maybe more*`

>howt to do this
>>>>instead of being accused
>who knows

-----

![awful picturep1](/test/p2.jpg)
![image relate](/pictures/p4.jpg)

- what
  
    **mak**
    nop
- nop
  - maybe

1. nop
    1.2 nop
2. nop

`import x from things can be pretty tough if`

```python
from numpy import randrom as rand
def bbb():
    pass

if
else

```

```flow

st=>start: 开始
op=>operation: My Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
&
```

![image][tmp]



```mermaid
graph LR
classDef node fill:#FFFF66,stroke:#3399FF,stroke-width:3px
    start[开始] --> input[输入A,B,C]
    input --> conditionA{A是否大于B}
    conditionA -- YES --> conditionC{A是否大于C}
    conditionA -- NO --> conditionB{B是否大于C}
    conditionC -- YES --> printA[输出A]
    conditionC -- NO --> printC[输出C]
    conditionB -- YES --> printB[输出B]
    conditionB -- NO --> printC[输出C]
    printA --> stop[结束]
    printC --> stop
    printB --> stop

```

```mermaid
graph LR
classDef node fill:#FFFF66,stroke:#3399FF,stroke-width:3px
    id1(Start)-->id2(Stop)
    style id1 fill:#f9f,stroke:#333,stroke-width:4px,fill-opacity:0.5
    style id2 fill:#ccf,stroke:#f36,stroke-width:3px,stroke-dasharray: 10,5
```

```mermaid
graph TB
classDef node fill:#FFFF66,stroke:#3399FF,stroke-width:3px
sequenceDiagram
A(Apple)-->B{Boy}
A---C(Cat)
B.->D((Dog))
C==喵==>D
style A fill:#00ff00,fill-opacity:0.1,stroke:#3399FF,stroke-width:2px
style D stroke:#000,stroke-width:8px;
```

```mermaid
    sequenceDiagram
    classDef default fill:#FFFF66,stroke:#3399FF,stroke-width:3px;
    participant 张 as 张三
    participant 李 as 李四
    participant 王 as  王五   
    张 ->> +李: 你好！李四, 最近怎么样?
    李-->> 王: 你最近怎么样，王五？
    李--x -张: 我很好，谢谢!
    activate 王
    李-x 王: 我很好，谢谢!   
    Note over 李,王: 李四想了很长时间, 文字太长了<br/>不适合放在一行.
    deactivate 王
    loop 李四再想想
    李-->>王: 我还要想想
    王-->>李: 想想吧
    end
    李-->>张: 打量着王五...
    张->>王: 很好... 王五, 你怎么样?

```
```mermaid
graph TB
    sq[Square shape] --> ci((Circle shape))

    subgraph A subgraph
        di{Diamond with  line break} -.-> ro(Rounded)
        di==>ro2(Rounded square shape)
    end

    e --> od3>Really long text with linebreak<br>in an Odd shape]

    cyr[Cyrillic]-->cyr2((Circle shape Начало));

    classDef green fill:#9f6,stroke:#333,stroke-width:2px;
    classDef orange fill:#f96,stroke:#333,stroke-width:4px;
    class sq,e green
    class di orange


```










```mermaid
gitGraph:
options
{
    "nodeSpacing": 150,
    "nodeRadius": 10
}
end
commit
branch newbranch
checkout newbranch
commit
commit
checkout master
commit
commit
merge newbranch
```


```python {cmd=true matplotlib=true}
import matplotlib.pyplot as plt
plt.plot([1,2,3,4])
plt.show() # show figure
```


```javascript {cmd="node"}
const date = Date.now()
console.log(date.toString())
```


```bash {cmd=true}
dir
```


```mermaid
graph LR
classDef node fill:#FFFF66,stroke:#3399FF,stroke-width:3px
 A === B
 A == This is the label text ==> B;
id1(Start)-->id2(Stop) 
```

















[tmp]:data:image/png;base64,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

#