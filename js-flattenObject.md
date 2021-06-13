### FLATTEN OBJECT JAVASCRIPT

## Example 1
```
flattenObject(obj, path = '', keys = []) {

    if (!(obj instanceof Object)) {
      if (keys.slice(0, keys.length - 1).includes(keys.slice(-1).toString())) {
        return { [path.replace(/\_$/g, '')]: obj }
      } else {
        return { [keys.slice(-1).toString()]: obj }
      }
    };

    return Object.keys(obj).reduce((output, key) => {
      keys.push(key);
      return obj instanceof Array ?
        { ...output, ...this.flattenObject(obj[key], '[' + key + ']_', keys) } :
        { ...output, ...this.flattenObject(obj[key], path + key + '_', keys) };
    }, {});

  }
```

## Example 2
```
var flatten = (a) => {  
  return a.reduce(function (flattened, item) {
    return flattened
      .concat([_.omit(item, "children")])
      .concat(item.children ? myFlat(item.children) : []);
  }, []);
}
```
