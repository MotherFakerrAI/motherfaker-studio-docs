# 📘 MotherFaker Studio 开发规范

> 统一团队开发标准，提高代码质量和协作效率

*版本：1.0.0 | 最后更新：2026-03-07*

---

## 📖 目录

- [命名规范](#-命名规范)
- [代码风格约定](#-代码风格约定)
- [Git 提交规范](#-git-提交规范)
- [文档撰写规范](#-文档撰写规范)

---

## 🏷️ 命名规范

### 文件命名

| 类型 | 规范 | 示例 |
|------|------|------|
| **源文件** | 小写 + 连字符 | `user-service.js` |
| **组件文件** | 大驼峰 | `UserProfile.jsx` |
| **测试文件** | 源文件名 + `.test` | `user-service.test.js` |
| **配置文件** | 小写 + 点号 | `.eslintrc.js` |
| **文档文件** | 小写 + 连字符 | `api-docs.md` |

### 变量命名

```javascript
// ✅ 正确
const userName = 'John';
const MAX_RETRY_COUNT = 3;
let isLoading = false;

// ❌ 错误
const userName1 = 'John';      // 避免无意义数字
const max = 3;                 // 含义不明确
let Loading = false;           // 布尔值应以 is/has/can 开头
```

### 函数命名

```javascript
// ✅ 正确
function getUserInfo() {}      // 获取数据用 get
function createUser() {}       // 创建用 create
function updateUser() {}       // 更新用 update
function deleteUser() {}       // 删除用 delete
function isValid() {}          // 判断用 is/has/can
function handleSubmit() {}     // 事件处理用 handle

// ❌ 错误
function userData() {}         // 动词缺失
function checkValid() {}       // 布尔函数应用 is
```

### 类命名

```javascript
// ✅ 正确
class UserService {}
class HttpClient {}
class DataProcessor {}

// ❌ 错误
class userService {}           // 应使用大驼峰
class User_Service {}          // 避免下划线
```

---

## 📐 代码风格约定

### JavaScript/TypeScript

```javascript
// 1. 使用 2 个空格缩进
function example() {
  const value = 1;
  return value;
}

// 2. 使用单引号
const name = 'MotherFaker';

// 3. 行尾不加分号（除必要情况）
const items = [1, 2, 3]

// 4. 箭头函数优先
const add = (a, b) => a + b

// 5. 使用模板字符串
const greeting = `Hello, ${name}!`

// 6. 对象简写
const name = 'John'
const user = { name }

// 7. 解构赋值
const { name, age } = user

// 8. 使用 const 优先，需要重新赋值时用 let
const PI = 3.14
let count = 0
count++
```

### CSS/样式

```css
/* 1. 使用连字符命名 */
.user-profile { }
.user-profile__avatar { }
.user-profile__avatar--large { }

/* 2. 属性按组排序 */
.element {
  /* 定位 */
  position: absolute;
  top: 0;
  
  /* 盒模型 */
  width: 100px;
  height: 100px;
  margin: 10px;
  padding: 10px;
  
  /* 样式 */
  background-color: #fff;
  color: #333;
}
```

### 代码组织

```javascript
// 1. 导入顺序
import React from 'react'                    // 第三方库
import { useState } from 'react'
import { UserService } from '@/services'     // 内部模块
import { formatDate } from '@/utils'
import './styles.css'                        // 样式文件

// 2. 导出顺序
export const constants = {}                  // 常量
export const utils = {}                      // 工具函数
export default Component                     // 默认导出
```

---

## 📝 Git 提交规范

### 提交格式

```
<type>(<scope>): <subject>

<body>

<footer>
```

### 类型说明

| 类型 | 说明 |
|------|------|
| `feat` | 新功能 |
| `fix` | Bug 修复 |
| `docs` | 文档更新 |
| `style` | 代码格式（不影响功能） |
| `refactor` | 重构（非新功能、非修复） |
| `test` | 测试相关 |
| `chore` | 构建/工具/配置 |
| `perf` | 性能优化 |
| `ci` | CI 配置 |

### 提交示例

```bash
# 新功能
git commit -m "feat(user): 添加用户登录功能"

# Bug 修复
git commit -m "fix(auth): 修复登录 token 过期问题"

# 文档更新
git commit -m "docs(readme): 更新安装指南"

# 重构
git commit -m "refactor(api): 重构 API 请求模块"

# 完整提交（带 body）
git commit -m "feat(search): 添加搜索功能

- 实现关键词搜索
- 添加搜索结果分页
- 优化搜索性能

Closes #123"
```

### 分支命名

```bash
# 功能分支
feature/user-login
feature/search-module

# 修复分支
fix/login-bug
fix/typo

# 发布分支
release/v1.0.0
release/2026-03

# 热修复分支
hotfix/critical-bug
```

---

## 📄 文档撰写规范

### 文档结构

```markdown
# {文档标题}

> {一句话描述}

## 概述

{详细说明}

## 快速开始

{入门指南}

## 详细说明

{核心内容}

## 常见问题

{FAQ}

## 参考资料

{相关链接}
```

### 写作规范

1. **标题层级**
   - 使用 `#` 到 `###`，避免过深
   - 标题应简洁明了

2. **代码块**
   - 始终指定语言类型
   - 添加必要注释

   ````markdown
   ```javascript
   // 示例代码
   const value = 1
   ```
   ````

3. **表格使用**
   - 表头清晰
   - 对齐一致

   ```markdown
   | 参数 | 类型 | 必填 | 说明 |
   |------|------|------|------|
   | name | string | 是 | 用户名 |
   ```

4. **链接规范**
   - 使用绝对链接或相对链接
   - 添加链接说明

   ```markdown
   [API 文档](./api.md) - 查看完整 API 说明
   ```

### 文档更新

- 在文档末尾添加更新时间
- 重大变更添加变更日志
- 保持文档与代码同步

---

## ✅ 检查清单

### 提交前检查

- [ ] 代码通过 lint 检查
- [ ] 测试通过
- [ ] 文档已更新
- [ ] 提交信息符合规范

### 发布前检查

- [ ] README 已更新
- [ ] 版本号已更新
- [ ] 变更日志已编写
- [ ] 所有测试通过

---

## 📚 参考资料

- [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

---

*本规范由 MotherFaker Studio 团队制定，所有成员应严格遵守。*
