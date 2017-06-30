Example of a bug in TypeScript's forceConsistentCasingInFileNames.

## Normal case:

```bash
cd CAPITALIZATION-IN-PATH
tsc -p tsconfig.json

# success
```

## Bug

```bash
cd CAPITALIZATION-IN-PATH
tsc -p config/tsconfig.json

1 import { doubleSpeed } from 'speed-doubler'
                              ~~~~~~~~~~~~~~~

src/lib/speed-doubler.spec.ts(1,29): error TS1149: File name '[...]/capitalization-in-path/src/index.ts' differs from already included file name '[...]/CAPITALIZATION-IN-PATH/src/index.ts' only in casing.
```
