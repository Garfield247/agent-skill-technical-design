# 可验证微任务拆解与铁证门禁 (Bite-Sized Tasks & Evidence Gate)

## 1. 可验证微任务拆解标准 (Bite-Sized Verifiable Tasks)

严禁方案中出现粗粒度的“步骤一：写代码；步骤二：测试”等半吊子规划。强制拆解为 10~20 分钟粒度的可检验原子任务：

### 1.1 微任务四要素标准结构
每个微任务必须包含四个核心属性：
1. **Target Files**：精确指明涉及的文件绝对/相对路径；
2. **Intent & Spec**：明确功能意图、接口入参与出参规范；
3. **Automated Verification**：精确、可直接粘贴执行的自动化检验命令；
4. **Evidence Gate**：命令预期输出证据（退出码 0、单测用例数 > 0、无 Race 警告）。

### 1.2 标准工程范例

```markdown
- [ ] **Task 1: [契约与数据模型定义]**
  - **Target Files**: `api/order.api`, `model/order_model.sql`
  - **Intent & Spec**: 声明 API 契约与 SQL Schema，建立防重唯一索引。
  - **Automated Verification**:
    ```bash
    goctl api validate --api api/order.api
    ```
  - **Evidence Gate**: 命令退出码 0，契约校验通过。

- [ ] **Task 2: [核心业务 Logic 编排与事务闭环]**
  - **Target Files**: `internal/logic/create_order_logic.go`
  - **Intent & Spec**: 实现下单编排、分布式防重锁与库存原子预扣。
  - **Automated Verification**:
    ```bash
    go test -v -run TestCreateOrderLogic_Success ./internal/logic/...
    ```
  - **Evidence Gate**: 单元测试 Pass，包含零库存与并发扣减测试。

- [ ] **Task 3: [异常分支覆盖与铁证回归]**
  - **Target Files**: `internal/logic/create_order_logic_test.go`
  - **Intent & Spec**: 覆盖超时回滚与重复提交幂等拦截分支。
  - **Automated Verification**:
    ```bash
    go test -v -race -cover ./internal/logic/...
    ```
  - **Evidence Gate**: 单测覆盖率 >= 80%，Race 竞态检测 0 警告。
```

---

## 2. 完成前铁证验证门禁 (Verification Evidence Gate)

### 2.1 铁证红线
- **严禁口头承诺完成**：在未取得真实命令执行成功证据前，严禁回复“已实现”、“已修复”、“没有问题”；
- **真实命令仲裁**：必须通过运行具体的单元测试、编译验证或 API 断言脚本作为唯一验收证据；
- **严禁静默兜底与重试**：单元测试必须真实覆盖报错分支并验证异常正确抛出，严禁在实现中用空指针兜底或吞异常。
