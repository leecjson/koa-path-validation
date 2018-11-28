# Start
```
npm i --save koa-path-validation
```

# Source code
```javascript
module.exports = async (ctx, next) => {
  if (ctx.path.startsWith('./') || ctx.path.startsWith('../') ||
    ctx.path.indexOf('/./') > 0 || ctx.path.indexOf('/../') > 0 || ctx.path.indexOf('\0') > 0) {
    ctx.throw(403);
  }
  await next();
}
```

