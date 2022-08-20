# angular-web3-modal

### shell

``` shell
npm install --save @walletconnect/web3-provider web3modal

npm install --save-dev @types/node @types/react assert https-browserify os-browserify stream-browserify stream-http url
```

### tsconfig.json

``` json
{
    // "allowSyntheticDefaultImports": false // change to true
    "allowSyntheticDefaultImports": true,
     "paths" : {
       "crypto": ["./node_modules/crypto-browserify"],
       "stream": ["./node_modules/stream-browserify"],
       "assert": ["./node_modules/assert"],
       "http": ["./node_modules/stream-http"],
       "https": ["./node_modules/https-browserify"],
       "os": ["./node_modules/os-browserify"],
     },
     "typeRoots": ["./node_modules/@types", "./src/types"]
}

```

### tsconfig.app.json
``` json
{
	"compilerOptions": {
		"types": ["node"],
		"module": "es2015",
	},
}
```

### src/polyfills.ts

``` ts
import { Buffer } from 'buffer';

(window as any).global = window;
(window as any).global.Buffer = (window as any).global.Buffer || require('buffer').Buffer;

global.process = {
    env: { DEBUG: undefined },
    version: '',
} as any;
```
