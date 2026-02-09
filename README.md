# alien-signals-getset

*forked from johnsoncodehk/alien-signals-starter to stablize API*

Use the `createReactiveSystem` API to build a simple signal library.

## Usage

`package.json` if using with Node/Bun/etc
```json
"dependencies": {
    "alien-signals-getset": "github:tomByrer/alien-signals-getset",
    ...
```
```ts
import { signal, computed, effect } from 'alien-signals-getset';

const count = signal(1);
const doubleCount = computed(() => count.get() * 2);

effect(() => {
  console.log(`Count is: ${count.get()}`);
}); // Console: Count is: 1

console.log(doubleCount.get()); // 2

count.set(2); // Console: Count is: 2

console.log(doubleCount.get()); // 4
```
Note, the `get`/`set` methods make it partly compatable with JavaScript [`Map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#instance_methods)  Those & `effect()` is all I need for my Finite State Machine usage in [state-shifter](https://github.com/tomByrer/state-shifter) .
