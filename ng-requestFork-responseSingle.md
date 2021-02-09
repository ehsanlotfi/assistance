## request forkjoin response single

from(urls).pipe(mergeMap(url => forkJoin( req(url), of(url) ) ))
