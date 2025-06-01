
# Mermaid 图表示例合集

以下展示了 Mermaid 的主要图表示例，包含从最基础的流程图，到复杂的 Git 图、需求图等。

---

## 1. 流程图 (Flowchart)

```mermaid
graph TD
  A[开始] --> B{是否继续？}
  B -->|是| C[继续执行]
  B -->|否| D[终止流程]
  C --> E[完成]
```

---

## 2. 时序图 (Sequence Diagram)

```mermaid
sequenceDiagram
  participant 用户
  participant 系统
  用户->>系统: 请求登录
  系统-->>用户: 返回验证码
  用户->>系统: 提交验证码
  系统-->>用户: 登录成功
```

---

## 3. 状态图 (State Diagram)

```mermaid
stateDiagram-v2
  [*] --> 空闲
  空闲 --> 活动中 : 开始
  活动中 --> 空闲 : 完成
  活动中 --> 错误 : 异常
  错误 --> 空闲 : 重置
```

---

## 4. 类图 (Class Diagram)

```mermaid
classDiagram
  Animal <|-- Dog
  Animal <|-- Cat
  class Animal {
    +String name
    +eat()
    +sleep()
  }
  class Dog {
    +bark()
  }
  class Cat {
    +meow()
  }
```

---

## 5. 实体关系图 (ER Diagram)

```mermaid
erDiagram
  CUSTOMER ||--o{ ORDER : places
  ORDER ||--|{ LINE_ITEM : contains
  CUSTOMER }|..|{ DELIVERY_ADDRESS : uses
```

---

## 6. 饼图 (Pie Chart)

```mermaid
pie title 项目占比
  "开发" : 40
  "测试" : 20
  "文档" : 15
  "运维" : 25
```

---

## 7. 甘特图 (Gantt Chart)

```mermaid
gantt
  title 项目时间表
  dateFormat  YYYY-MM-DD
  section 规划
    需求分析     :a1, 2025-06-01, 3d
    设计阶段     :after a1  , 4d
  section 实施
    编码         :2025-06-08, 5d
    测试         :2025-06-14, 3d
```

---

## 8. Git 图 (Git Graph)

```mermaid
gitGraph
  commit
  commit
  branch develop
  checkout develop
  commit
  branch feature
  checkout feature
  commit
  checkout develop
  merge feature
  checkout main
  merge develop
```

---

## 9. 用户旅程图 (User Journey)

```mermaid
journey
  title 用户注册流程
  section 打开网站
    用户->网站: 浏览首页
  section 注册
    用户->网站: 填写注册表单
    网站->用户: 邮件验证
    用户->网站: 完成注册
```

---

## 10. 需求图 (Requirement Diagram)

```mermaid
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you ?
    Bob->>Alice: Fine, thank you. And you?
    create participant Carl
    Alice->>Carl: Hi Carl!
    create actor D as Donald
    Carl->>D: Hi!
    destroy Carl
    Alice-xCarl: We are too many
    destroy Bob
    Bob->>Alice: I agree

```

---
