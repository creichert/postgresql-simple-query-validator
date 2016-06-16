# postgresql-simple-query-validator
Validate SQL statements embedded in postgresql-simple's quasiquoter against a PostgreSQL server.

# Why this exists

So I don't have to wait till an integration test or run-time to figure out
whether a query I wrote or modified is valid (syntax and structure).

Also, swapping '?'s and actual data is a pain.

**No more SQL syntax errors or incorrect column/table names in source code :)**

# Requirements

- [stack](http://docs.haskellstack.org/en/stable/README/)

# Usage

`./validate.hs src/App/Queries.hs postgresql://user:password@host/dbname`

Errors, if any, will be printed to stdout and the exit code will be non-zero.

# Other usage

- integrate this into your build so that it fails if there is a bad query
- watch for source changes with [entr](http://entrproject.org/), run this
  script, and send a notification accordingly with `notify-send`
