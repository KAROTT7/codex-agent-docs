# CSS / Tailwind CSS / Less

- 优先沿用项目现有样式方案；已有 Tailwind 时，布局、间距和栅格优先使用 Tailwind。
- 覆盖第三方组件时优先使用主题 token、组件 props 或局部 Less，避免全局高优先级选择器。
- 不新增独立设计系统，不使用大段不可维护的内联样式。
- 保证文本在移动端和桌面端不溢出或重叠；固定格式控件使用稳定尺寸和响应式约束。
- 遵循现有颜色、间距、圆角和排版变量，避免无依据的视觉重构。

## Tailwind CSS 配套依赖

- 项目已安装 Tailwind CSS 时，同时安装并配置与当前 Tailwind 版本兼容的 `tailwindcss-safe-area`，使用其工具类适配安全区域。
- 安装 `tailwind-merge` 和 `clsx`，使用 `clsx` 组织条件类名，再通过 `tailwind-merge` 合并 Tailwind 冲突类名，如 `twMerge(clsx(...inputs))`。
- 优先复用项目已有的类名合并工具（如 `cn`）；缺少时统一封装，避免在组件中重复实现。依赖已存在时直接复用，缺少时使用项目现有包管理器补齐。
