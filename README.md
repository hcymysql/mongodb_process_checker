https://www.mydbops.com/blog/mongodb-process-list-in-mysql-way/

# 实时监控MongoDB运行状态，就像你在MySQL里，执行show processlist一样。
  
```
shell> ./mongodb_process_checker --help
Mongo Process Checker

options:
  -h, --help            show this help message and exit
  -H MONGO_HOST, --host MONGO_HOST
                        Input Hostname, Default: localhost
  -P MONGO_PORT, --port MONGO_PORT
                        Input Port, Default: 27017
  -u MONGO_USER, --user MONGO_USER
                        Input Username, Default: NoAuth
  -p MONGO_PASSWORD, --password MONGO_PASSWORD
                        Input Password, Default: NoAuth
  -a AUTHDB, --authDB AUTHDB
                        Input Auth DB, Default: admin
  -i REFRESH_RATE, --interval REFRESH_RATE
                        Input Refresh Interval (Sec), Default: 4 Sec
  -k KILL, --kill KILL  Input Value To Kill Queries Exceeding X Sec
  --dry-run             Just Print Queries Exceeding X Sec
  -v, --verbose         Print OpCounter, Document Stats
  -r, --repl            Print Replication Info

shell> ./mongodb_process_checker -H 192.168.176.204 -P 37017 -u admin -p 123456 -a admin -r -v
```
![mongo_process](https://github.com/user-attachments/assets/2cc3eafe-30da-401b-b5e2-4c3825ed5be7)

### MongoDB账号权限：
```
use admin
db.createUser({user:"admin",pwd:"123456",roles:[{role:"root",db:"admin"}]})
```
