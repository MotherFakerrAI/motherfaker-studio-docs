# 💻 代码规范

> MotherFaker Studio 统一代码质量和测试标准

*版本：1.0.0 | 最后更新：2026-03-07*

**来源仓库：** https://github.com/MotherFakerrAI/code-standards

---

## 📖 目录

- [快速开始](#-快速开始)
- [ESLint 配置](#-eslint-配置)
- [AAA 测试模板](#-aaa-测试模板)
- [测试命名规范](#-测试命名规范)
- [CI/CD 集成](#-cicd-集成)

---

## 🚀 快速开始

### 1. 安装依赖

```bash
npm install -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
npm install -D jest @types/jest
```

### 2. 复制配置文件

```bash
# ESLint 配置
cp node_modules/@motherfaker/code-standards/eslint.config.js ./

# 测试模板
cp node_modules/@motherfaker/code-standards/test-template.js ./tests/
```

### 3. 配置 package.json

```json
{
  "scripts": {
    "lint": "eslint .",
    "lint:fix": "eslint . --fix",
    "test": "jest",
    "test:watch": "jest --watch"
  }
}
```

### 4. 运行检查

```bash
# 检查所有文件
npx eslint .

# 自动修复
npx eslint . --fix

# 运行测试
npm test
```

---

## 🔧 ESLint 配置

### 核心规则

#### 1. 命名规范

**变量名必须有意义，禁止无意义命名**

```javascript
// ❌ 错误：无意义变量名
const data = getUser();
const obj = {};
const val = 100;

// ✅ 正确：有意义的命名
const userData = getUser();
const userPreferences = {};
const maxRetryCount = 100;
```

**禁止的变量名：**
- `data`, `info`, `result`, `output`, `input`
- `obj`, `val`, `tmp`, `err`

#### 2. 函数参数限制（≤ 3 个）

```javascript
// ❌ 错误：参数过多
function createUser(name, email, age, address, phone, role) {
  // ...
}

// ✅ 正确：使用对象参数
function createUser({ name, email, age, address, phone, role }) {
  // ...
}
```

#### 3. 显式优于隐式

```javascript
// ❌ 错误：隐式类型转换
const isValid = !!value;
const num = +str;
const hasName = user.name ? true : false;

// ✅ 正确：显式转换
const isValid = Boolean(value);
const num = Number(str);
const hasName = Boolean(user.name);
```

#### 4. 禁止魔术数字

```javascript
// ❌ 错误：魔术数字
if (user.age > 18) {
  const total = price * 1.1;
}

// ✅ 正确：使用常量
const LEGAL_ADULT_AGE = 18;
const TAX_RATE = 1.1;

if (user.age > LEGAL_ADULT_AGE) {
  const total = price * TAX_RATE;
}
```

### 配置说明

| 规则 | 说明 | 级别 |
|------|------|------|
| `id-denylist` | 禁止无意义变量名 | Error |
| `max-params` | 函数参数 ≤ 3 个 | Error |
| `no-implicit-coercion` | 禁止隐式类型转换 | Error |
| `no-magic-numbers` | 禁止魔术数字 | Warn |
| `prefer-const` | 优先使用 const | Error |
| `complexity` | 函数复杂度 ≤ 10 | Warn |
| `max-lines-per-function` | 函数 ≤ 50 行 | Warn |
| `max-depth` | 嵌套深度 ≤ 4 | Error |

---

## 🧪 AAA 测试模板

### AAA 模式结构

```
┌─────────────────┐
│   Arrange       │  准备测试数据和环境
├─────────────────┤
│   Act           │  执行被测试的操作
├─────────────────┤
│   Assert        │  验证结果是否符合预期
└─────────────────┘
```

### 完整示例

```javascript
describe('UserService', () => {
  describe('getUserById', () => {
    it('should_return_user_when_id_exists', async () => {
      // ========== Arrange ==========
      const userId = '123';
      const mockUser = { id: userId, name: 'John' };
      const dbMock = { findById: jest.fn().mockResolvedValue(mockUser) };
      const userService = new UserService(dbMock);
      
      // ========== Act ==========
      const result = await userService.getUserById(userId);
      
      // ========== Assert ==========
      expect(result).toBeDefined();
      expect(result.id).toBe(userId);
      expect(dbMock.findById).toHaveBeenCalledWith(userId);
    });

    it('should_throw_error_when_id_not_found', async () => {
      // ========== Arrange ==========
      const userId = '999';
      const dbMock = { findById: jest.fn().mockResolvedValue(null) };
      const userService = new UserService(dbMock);
      
      // ========== Act & Assert ==========
      await expect(userService.getUserById(userId))
        .rejects
        .toThrow('User not found');
    });
  });
});
```

---

## 📝 测试命名规范

### 格式

```
should_预期行为_when_场景_预期结果
```

### 示例

```javascript
// ✅ 好的命名
it('should_return_user_when_id_exists')
it('should_throw_error_when_id_not_found')
it('should_calculate_total_price_with_tax')
it('should_be_disabled_when_disabled_prop_is_true')

// ❌ 差的命名
it('test user')
it('works correctly')
it('handles error')
```

### 命名模式

| 场景 | 命名模式 | 示例 |
|------|----------|------|
| **成功场景** | `should_return_X_when_Y` | `should_return_user_when_id_exists` |
| **错误场景** | `should_throw_error_when_Y` | `should_throw_error_when_id_not_found` |
| **状态变化** | `should_be_X_when_Y` | `should_be_disabled_when_loading` |
| **计算场景** | `should_calculate_X_when_Y` | `should_calculate_total_with_tax` |

---

## ✅ 测试检查清单

编写测试前检查：

- [ ] 测试命名是否清晰描述了场景和预期？
- [ ] 是否遵循 AAA 模式（三段式结构）？
- [ ] Arrange 部分是否独立（不依赖外部状态）？
- [ ] Act 部分是否只执行一个操作？
- [ ] Assert 部分是否有明确的断言？
- [ ] 是否测试了边界条件和错误情况？
- [ ] 测试是否可重复运行（无副作用）？
- [ ] 是否使用了有意义的变量名？

---

## 🔗 CI/CD 集成

### GitHub Actions 示例

```yaml
# .github/workflows/ci.yml
name: CI

on: [push, pull_request]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - run: npm install
      - run: npm run lint

  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - run: npm install
      - run: npm test
```

---

## 📚 参考资源

- [ESLint 官方文档](https://eslint.org/docs/)
- [TypeScript ESLint](https://typescript-eslint.io/)
- [Jest 测试框架](https://jestjs.io/)
- [AAA 测试模式](https://medium.com/@jamischarles/what-is-aaa-testing-arrange-act-assert-14684a9702fa)

---

*Made with ❤️ by MotherFaker Studio*
