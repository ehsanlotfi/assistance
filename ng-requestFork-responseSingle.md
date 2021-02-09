## request forkjoin response single

```
import { Observable, forkJoin, from, of } from 'rxjs';
import { mergeMap } from "rxjs/operators";
```

```
from(urls).pipe(mergeMap(url => forkJoin( req(url), of(url) ) ))
```
