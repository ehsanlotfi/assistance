### set id == 0
```
datas
	.Select(x=>Regex.Replace(JsonConvert.SerializeObject(x), @"(?<=""Id"":)\d+(?=,)", "0"))
	.Select(x=>JsonConvert.DeserializeObject<Irisdata>(x))
```
