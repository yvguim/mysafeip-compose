# mysafeip-compose

This is a simple repository to deploy mysafeip server with docker-compose

Clone repository:
<code>
git clone https://github.com/yvguim/mysafeip-compose.git
</code>

Go to mysafeip-compose directory and create an empty sql_app.db file.
<code>
cd mysafeip-compose && touch sql_app.db
</code>
  
Edit env file to suit your needs and in priority:
JWT_SECRET
URL_WEBSITE

Pull and launch mysafeip docker container:
<code>
docker compose pull ; docker compose up -d
</code>

You can check all is ok with the log command:
<code>
docker logs mysafeip 
</code>

Init admin account and password:
<code>
docker exec -it mysafeip python3 /app/init_admin.py yves.guimard@gmail.com Your_super_secret_password!
</code>

Now your mysafeip server is available. Try it your web browser: http://your_url

To use it with https, consider caddy container for example ;)

Tips to update to latest mysafeip version:
<code>
docker compose down ; docker compose pull ; docker compose up -d
</code>
