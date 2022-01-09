```javascript
const value = 1;
const a = () =>{
    const value = 10;
    console.log(value);
    b()
}

const b = () =>{
    console.log(value);
}

a()
b()

```
```console
10
1
1
```