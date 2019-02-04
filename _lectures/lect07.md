---
num: lect07
desc: "Deployment Tips"
lecture_date: 2019-02-04
ready: true
---

# Web App Folks

Be careful about your database choice.

If you are planning to deploy to Heroku:

* Avoid tutorials based on `sqlite3`
* Instead, find tutorials based on `postgres` (`psycopg2`)
* Better yet, use a library at a higher layer of abstraction
   * `SQLAlchemy`, `alembic`, etc.
* Avoid low level SQL:
   * There are little "gotchas" with SQL dialects
   * SQL is portable in principle, but not in practice!
   * Examples: `AUTOINCREMENT` vs. `SERIAL`, `user` being a keyword, etc. 
   
Of course, you are also free to deploy on another platform.  
* In general, there's no free lunch; you have to choose which battle to fight.

# Unit Testing, Integration Testing, Test Coverage

Demo of Flask Tutorials Test Coverage report