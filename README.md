# Cooruja-mongodb-setup

- Connect localhost (without user, pwd) on database admin
```
mongodb://localhost:27017/admin
```
- Open >MONGOSH (shell) and create your user
```
db.createUser({ 
	user:  "<username>", 
	pwd: "<passoword>", 
	roles: [ { role: 'root', db: "admin" } ] 
});
```
- Check your user authenticate success
```
db.auth("<username>","<passoword>")
```

### Docker compose
- Add --auth on entrypoint
```
entrypoint: ['/usr/bin/mongod', '--bind_ip', '0.0.0.0','--auth']
```
