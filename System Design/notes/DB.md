# Database

### Index
  - Index is basically storage-time trade off
  - more storage
  - faster read query, slower write/update query

```
explain analyse select * from person;

create index person_first_name on person(first_name);

explain analyse select * from person where first_name = 'Ali';

explain analyse select * from person where last_name = 'Adams';

explain analyse select * from person where first_name = 'Ali' and last_name = 'Adams';

explain analyse select * from person where first_name = 'Ali' or last_name = 'Adams';

```

Type of scan -
- Index scan
- Bitmap index scan https://pganalyze.com/docs/explain/scan-nodes/bitmap-index-scan
- Bitmap heap scan
- Sequential scan
