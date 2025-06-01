
# Mermaid 示例文档

下面展示了 Mermaid 支持的各种图表类型。

---

## 1. Flowchart (流程图)

```mermaid
flowchart TD
    A[开始] --> B{条件判断}
    B -- 是 --> C[处理 A]
    B -- 否 --> D[处理 B]
    C --> E[结束]
    D --> E
```

---

## 2. Sequence Diagram (时序图)

```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>Bob: 你好！
    Bob-->>Alice: 嗨，最近怎么样？
```

---

## 3. Gantt Chart (甘特图)

```mermaid
gantt
    title 项目开发进度
    dateFormat  YYYY-MM-DD
    section 设计
    需求分析      :a1, 2025-06-01, 3d
    原型设计      :after a1, 5d
    section 开发
    后端开发      :2025-06-10, 10d
    前端开发      :2025-06-15, 8d
    section 测试
    单元测试      :2025-06-25, 4d
    集成测试      :2025-06-28, 4d
```

---

## 4. Class Diagram (类图)

```mermaid
classDiagram
    Animal <|-- Dog
    Animal <|-- Cat
    Animal : +String name
    Animal : +makeSound()
    Dog : +bark()
    Cat : +meow()
```

---

## 5. State Diagram (状态图)

```mermaid
stateDiagram
    [*] --> 空闲
    空闲 --> 运行中 : 用户点击
    运行中 --> 暂停 : 暂停按钮
    暂停 --> 运行中 : 继续
    运行中 --> 结束 : 完成任务
    结束 --> [*]
```

---

## 6. ER Diagram (实体关系图)

```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE_ITEM : contains
    CUSTOMER {
        string name
        string address
    }
    ORDER {
        int id
        string date
    }
```

---

## 7. Pie Chart (饼图)

```mermaid
pie
    title 浏览器市场份额
    "Chrome" : 64
    "Safari" : 19
    "Firefox" : 4
    "Edge" : 3
    "其他" : 10
```

---

## 8. Mind Map (思维导图)

```mermaid
mindmap
  root
    学习
      编程
        Python
        JavaScript
      数学
        代数
        几何
    健康
      饮食
      运动
```

---

## 9. Git Graph (Git 图)

```mermaid
gitGraph
    commit
    commit
    branch develop
    checkout develop
    commit
    commit
    checkout main
    merge develop
```

---

## 10. Timeline (时间线)

```mermaid
timeline
    title AI 发展史
    1950 : 图灵测试
    1997 : IBM 深蓝击败卡斯帕罗夫
    2016 : AlphaGo 击败李世石
    2023 : GPT-4 发布
```

---

## 11. User Journey (用户旅程图)

```mermaid
journey
    title 购物流程
    section 浏览商品
      用户 -> 商城 : 浏览页面
    section 添加到购物车
      用户 -> 商城 : 添加商品
    section 下单
      用户 -> 商城 : 提交订单
    section 支付
      用户 -> 支付系统 : 完成支付
```
