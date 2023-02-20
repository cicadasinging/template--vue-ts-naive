# template--vue-ts-naive

模版仓库，技术栈：Vue 全家桶、TypeScript、Naive UI。

## Project Setup

```sh
pnpm install
```

### Compile and Hot-Reload for Development

```sh
pnpm dev
```

### Type-Check, Compile and Minify for Production

```sh
pnpm build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
pnpm test:unit
```

### Lint with [ESLint](https://eslint.org/)

```sh
pnpm lint
```

## Template Setup

### [Naive UI](https://www.naiveui.com/zh-CN/os-theme/docs/installation)

```sh
pnpm add -D naive-ui
```

#### [07akioni](https://github.com/07akioni)/**[vfonts](https://github.com/07akioni/vfonts)**

```sh
pnpm add -D vfonts
```

`main.ts`:

```typescript
// 通用字体
import "vfonts/Lato.css";
// 等宽字体
// import "vfonts/FiraCode.css";
```

#### [07akioni](https://github.com/07akioni)/**[xicons](https://github.com/07akioni/xicons)**

```
pnpm add -D @vicons/fluent
```

`vite.config.ts`:

```typescript
const _regexp = new RegExp("^[A-Z][a-zA-Z]*([a-z][1-9]\\d[A-Z])[a-zA-Z]*[a-z]$");

export default defineConfig(() => {
  return {
    plugins: [
      Components({
        resolvers: [(name) => (_regexp.test(name) ? { name, from: "@vicons/fluent" } : "")],
      }),
    ],
  };
});
```
