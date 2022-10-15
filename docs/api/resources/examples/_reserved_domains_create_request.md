
#### Example Request

```bash 
curl \
-H "Authorization: Bearer {API_KEY}" \
-H "Content-Type: application/json" \
-H "Ngrok-Version: 2" \
-d '{"name":"myapp.mydomain.com","region":"us","certificate_id":"cert_2EmMOjyjtRQxXJlOZ7UEIehvuJt"}' \
https://api.ngrok.com/reserved_domains