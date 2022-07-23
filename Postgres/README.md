# Lowdefy Getting Started Tutorial (Postgres)

Created to learn more about Lowdefy, This project takes the getting started guide and uses Postgres as a backend for the data instead of Google Sheets.

Link to original instructions: https://docs.lowdefy.com/tutorial-start

## Setup
### Postgres
Create a new Postgres Database and run the query below to create the schema
```
CREATE TABLE tickets (
	id BIGSERIAL,
	title TEXT,
	description TEXT,
	ticket_type VARCHAR(50),
	restarted BOOL,
PRIMARY KEY(id));
```

### Lowdefy
Copy `example.env` as `.env` and update the values to match your environment
`LOWDEFY_SECRET_PG_HOST` - Your Postgres server IP or Hostname
`LOWDEFY_SECRET_PG_PORT` - The port for your database
`LOWDEFY_SECRET_PG_DB` - The name of your database
`LOWDEFY_SECRET_PG_USER` - Your postgres username
`LOWDEFY_SECRET_PG_PASS` - Your postgres password

### Checklist
- [ ] - Postgres Database created
- [ ] - Postgres Schema created
- [ ] - `example.env` copied to `.env`
- [ ] - Environment variables changed in `.env`

## Running
This can be ran with the Lowdefy dev server command
```
npx lowdefy@latest dev
```

## Notes
When submitting if you see an error about not being able to find or install `pg` you can run `npm install pg --save` to get around it.