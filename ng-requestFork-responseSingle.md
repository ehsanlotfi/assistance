## request forkjoin response single
```
const req: Observable[] = []
 from().pipe(
    mergeMap((observable, index) => observable.pipe(
      map(value => ({ value, index })),
    )),
  ).subscribe(res =>
  {
    debugger
  });
```
