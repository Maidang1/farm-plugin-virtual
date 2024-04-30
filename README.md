# farm-plugin-virtual

Inspired By [@rollup/plugin-virtual](https://www.npmjs.com/package/@rollup/plugin-virtual)

A rust plugin for farm to easily use virtual module

## install

```bash
pnpm add -D farm-plugin-virtual
```

## Usage

farm.config.ts

```typescript
import { defineConfig } from '@farmfe/core';

export default defineConfig({
  plugins: [
    [
      'farm-plugin-virtual',
      {
        'virtual-module': 'export const a = 1',
        'src/01.js': 'export const module01 = "virtual-module from 01.js"',
      },
    ],
  ],
});
```

index.js

```javascript
import { a } from 'virtual-module';
```

src/02.js

```javascript
import { module01 } from './01.js';
```
