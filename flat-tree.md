
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
        if (node[parent_key] && (Number(map[node[parent_key]]) == map[node[parent_key]])) {
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
const flattenDeep = (items, path = "", index = 0) => (
  items.reduce((acc, val) => {
    if (val.children && val.children.length) {
      val.path = path || null;
      val.treeIndex = ++index;
      acc.push(val);
      return acc.concat(flattenDeep(val.children, val.treeIndex, index));
    }
    val.path = path;
    val.treeIndex = ++index;
    return acc.concat(val);
  }, [])
);

```
