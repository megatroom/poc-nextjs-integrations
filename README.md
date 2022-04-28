# poc-nextjs-integrations

POC to test multi Next.js project under NGINX

## How initialize project

First of all you need set this variable on your terminal.

```bash
# For Linux users:
export DOCKERHOST=$(ip -4 addr show docker0 | grep -Po 'inet \K[\d.]+')

# For MacOS users:
export DOCKERHOST=$(ipconfig getifaddr en0)
```

And to run use:

```bash
docker-compose up
```

## Routes

| Route | Project | Description |
| --- | --- | --- |
| [/](http://localhost:3000) | root | Generic blog |
| [/parana](http://localhost:3000/parana) | parana | NextJS app for Paraná state |
| [/riodejaneiro](http://localhost:3000/riodejaneiro) | rio-de-janeiro | NextJS app for Rio de Janeiro state |
| [/404](http://localhost:3000/404) | root | Static not found error page for all aplications |
| [/500](http://localhost:3000/500) | root | Static internal server error page for all aplications. For errors 500 and 502 |