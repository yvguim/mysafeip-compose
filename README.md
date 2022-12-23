# mysafeip-compose

This is a simple repository to deploy mysafeip server with docker-compose.
Installation is straight forward and take 5 minutes.

Clone repository:
```
git clone https://github.com/yvguim/mysafeip-compose.git
```

Go to mysafeip-compose directory and create an empty sql_app.db file.
```
cd mysafeip-compose && touch sql_app.db
```

Edit env file to suit your needs and in priority:
```
JWT_SECRET
URL_WEBSITE
```

Pull and launch mysafeip docker container:
```
docker compose pull ; docker compose up -d
```

You can check that all is ok with the log command:
```
docker logs mysafeip 
```

Initialize admin account and password:
```
docker exec -it mysafeip python3 /app/init_admin.py yves.guimard@gmail.com Your_super_secret_password!
```

Now your mysafeip server is available. Try it in your web browser: http://your_url and login with the account created previously.

You can now secure your authentication by enabling TOTP and create a token for your client:

Now, you can configure your mysafeip-client: [https://github.com/yvguim/mysafeip-client]
