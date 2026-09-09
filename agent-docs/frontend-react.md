# React / TypeScript

- 默认使用 TypeScript、函数组件和 Hooks。
- 组件优先使用 `function ComponentName()` 声明；需要默认导出时，使用 `export default function ComponentName()`。高阶组件包装等特殊情况沿用项目写法。
- 默认不启用 React 严格模式（`StrictMode`）。
- 组件保持单一职责；复杂逻辑提取到 hooks 或 service 层。
- 页面内部的展示片段在至少两处实际使用前，默认不单独封装组件；确需隔离复杂状态、生命周期或独立业务职责时可以拆分，不以缩短文件或预想复用为唯一理由。
- 状态管理遵循就近原则：局部状态优先，其次提升、context 或 store。
- 能从 props、现有状态或接口数据计算出的派生值，优先直接计算，不重复存储为状态；计算成本确有需要时再使用 `useMemo`，避免多份状态需要手动同步。
- 能不用 `any` 就不用；优先使用类型守卫、判别联合和 schema 推断，避免粗暴断言。
- 涉及浏览器 API 时遵守 SSR / hydration 边界；仅在需要交互或浏览器 API 时使用客户端组件。
