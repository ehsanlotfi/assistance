## request forkjoin response single
```
const req: Observable[] = []
 from(req).pipe(
    mergeMap((observable, index) => observable.pipe(
      map(value => ({ value, index })),
    )),
  ).subscribe(res =>
  {
    debugger
  });
```
