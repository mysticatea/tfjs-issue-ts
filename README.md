# TensorFlow.js TypeScript issue

The simple following code doesn't work:

```ts
import * as tf from "@tensorflow/tfjs"
```

```
node_modules/@tensorflow/tfjs-layers/dist/models.d.ts:27:5 - error TS2416: Property 'build' in type 'Sequential' is not assignable to the same property in base type 'Model'.
  Type '(inputShape?: number[] | undefined) => void' is not assignable to type '(inputShape: number[] | number[][]) => void'.
    Types of parameters 'inputShape' and 'inputShape' are incompatible.
      Type 'number[] | number[][]' is not assignable to type 'number[] | undefined'.
        Type 'number[][]' is not assignable to type 'number[] | undefined'.
          Type 'number[][]' is not assignable to type 'number[]'.
            Type 'number[]' is not assignable to type 'number'.

27     build(inputShape?: Shape): void;
       ~~~~~


Files:          109
Lines:        26569
Nodes:       137798
Identifiers:  47922
Symbols:      48472
Types:        14570
Memory used: 80854K
I/O read:     0.03s
I/O write:    0.00s
Parse time:   0.52s
Bind time:    0.21s
Check time:   1.08s
Emit time:    0.00s
Total time:   1.81s
```

## Repro steps

```
git clone https://github.com/mysticatea/tfjs-issue-ts.git
cd tfjs-issue-ts
npm install
npm run build
```
