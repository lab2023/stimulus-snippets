```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer components {
  .tab-link {
    @apply
    font-medium font-bold text-xs
    border-x-0 border-t-0 border-b-2 border-gray-200
    px-1
    py-3
  }
  .tab-active {
    @apply
    border-blue-500
  }
}
```