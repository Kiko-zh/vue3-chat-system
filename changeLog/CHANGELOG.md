# 0.0.0

## 创建项目

```bash
# https://cn.vitejs.dev/guide/
yarn create vite vue3-chat-system --template vue-ts

# install
- yarn install
- yarn

# run dev
- yarn dev
```
![create_vue-ts](./imgs/create_vue-ts.png)

### node_modules
```bash
- @vitejs/plugin-vue # 用于编辑vue文件
- vue-tsc # 专用 vue3项目的 Typescript类型检查工具
```

## 格式化代码

### 文件介绍
![配置参考链接](https://juejin.cn/post/7091216449171095588)

- `.editorconfig`: 用于确保基本的编码风格在不同编辑器间保持一致
- `eslint`: 更深入分析code，确保code质量，符合特定的编码规范
- `prettier`: 自动格式化code，确保code风格的一致性
- `.browserslistrc`: 定义目标浏览器，确保在这些浏览器中，Application可以正常工作

```bash
yarn add eslint prettier eslint-config-prettier eslint-plugin-prettier eslint-plugin-vue @typescript-eslint/eslint-plugin @typescript-eslint/parser -D
```

### 使用husky lint-staged

```bash
yarn add husky lint-staged -D
```

```js
// 新增scripts in package.json
scripts: {
  // ...
  "prepare": "husky install"
}
```

```bash
- yarn prepare # install husky
- npx husky add .husky/pre-commit "lint-staged"
```

### 清除npm cache

若是 eslint 没有生效，先clear cache
```bash
npx eslint --cache --cache-location './.eslintcache' --ext .js,.ts,.vue --fix .
```

