
# Flatten To Tree
```
function flatToTree(list, entity_key, parent_key) {
    var map = {}, node, roots = [], i;

    for (i = 0; i < list.length; i += 1) {
      map[list[i][entity_key]] = i;
      list[i].children = [];
    }

    for (i = 0; i < list.length; i += 1) {
      node = list[i];
      if (node[parent_key]) {
        list[map[node[parent_key]]].children.push(node);
      } else {
        roots.push(node);
      }
    }
    return roots;
  }
```

# Tree To Flatten
```
const treeToFlat = (items) => (
  items.reduce((acc, val) => {
    if (val.children && val.children.length) {
      acc.push(val);
      return acc.concat(flattenDeep(val.children));
    }
    return acc.concat(val);
  }, [])
);
```
