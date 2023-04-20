# 手写简化版Promise

仅实现了第一个`.then()`

```javascript
class Promise2 {
  #status = 'pending';
  q = [];
  constructor(fn) {
    const resolve = (data) => {
      this.#status = 'fulfilled';
      const f1f2 = this.q.shift();
      if (!f1f2 || !f1f2[0]) return;
      const x = f1f2[0].call(undefined, data);
      if (x instanceof Promise2) {
        x.then(
          (data) => {
            resolve(data);
          },
          (reason) => {
            reject(reason);
          }
        );
      } else {
        reject(x);
      }
    };
    const reject = (reason) => {
      this.#status = 'rejected';
      const f1f2 = this.q.shift();
      if (!f1f2 || !f1f2[1]) return;
      const x = f1f2[1].call(undefined, reason);
      if (x instanceof Promise2) {
        x.then(
          (data) => {
            resolve(data);
          },
          (reason) => {
            reject(reason);
          }
        );
      } else {
        reject(x);
      }
    };
    fn.call(undefined, resolve, reject);
  }
  then(f1, f2) {
    this.q.push([f1, f2]);
  }
```
