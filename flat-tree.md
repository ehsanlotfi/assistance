
# Flat To Tree
```
function flattotree(arr, parent_id) {
    var out = []
    for(var i in arr) {
        if(arr[i].parent == parent_id) {
            var children = getNestedChildren(arr, arr[i].id)

            if(children.length) {
                arr[i].children = children
            }
            out.push(arr[i])
        }
    }
    return out
}
```

# Tree To Flat
```
const treetoflat = (items) => (
  items.reduce((acc, val) => {
    if (val.children && val.children.length) {
      acc.push(val);
      return acc.concat(flattenDeep(val.children));
    }
    return acc.concat(val);
  }, [])
);
```
