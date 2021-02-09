## request forkjoin response single

```
import { forkJoin, from, Observable, of, merge, race } from 'rxjs';
```

```
from(urls).pipe(mergeMap(url => forkJoin( req(url), of(url) ) ))
```
