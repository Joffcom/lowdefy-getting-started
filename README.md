# Lowdefy Getting Started Tutorial (Baserow)

Created to learn more about Lowdefy, This project takes the getting started guide and uses Baserow as a backend for the data instead of Google Sheets.

Link to original instructions: https://docs.lowdefy.com/tutorial-start

## Setup
### Baserow
Create a new Baserow Table with the following Fields
- Title
  - Single Line Text
- Description
  - Long Text
- Type
  - Single Select
    - Feature Request
    - Bug Report
    - Question
- Restarted
  - Single Select
    - Yes
    - No

It will look something like this:
<img width="767" alt="image" src="https://user-images.githubusercontent.com/640846/179925701-720254a0-9380-4958-a660-099b33babe79.png">

View the automatically generated API docs and make a note of the values for Restarted and Type, These will be numbers. Also make a note of your Table URL and your API Token.

### Lowdefy
Copy `example.env` as `.env` and set the value of `LOWDEFY_SECRET_BASEROW_API_KEY` to the Base64 encoded version of your token with the Token prefix. If your API token is `CorrectHorseBatteryStable` you would encode `Token CorrectHorseBatteryStable` which would give you a result of `VG9rZW4gQ29ycmVjdEhvcnNlQmF0dGVyeVN0YXBsZQ==`

Update `lowdefy.yaml` changing the `baseURL` to the base URL for your Baserow installation.

Edit `new-ticket.yaml` changing the value of `[TABLE_ID]` to match the table ID from the table URL you got from Baserow. Replace `747` with the number for your Single Select No value and `746` with the value for Yes. The last 3 changes are `743`, `744` and `745` which will need to be changed to the single select values for the ticket Types.

### Checklist
- [ ] - Baserow table made with fields
- [ ] - `example.env` copied to `.env`
- [ ] - `LOWDEFY_SECRET_BASEROW_API_KEY` value changed to a base64 encoded version version of `Token YOUR_BASEROW_API_KEY`
- [ ] - `baseURL` changed in `lowdefy.yaml`
- [ ] - `[TABLE_ID]` replaced in `new-ticket.yaml`
- [ ] - `747` replaced in `new-ticket.yaml`
- [ ] - `746` replaced in `new-ticket.yaml`
- [ ] - `743` replaced in `new-ticket.yaml`
- [ ] - `744` replaced in `new-ticket.yaml`
- [ ] - `745` replaced in `new-ticket.yaml`

## Running
This can be ran with the Lowdefy dev server command
```
npx lowdefy@latest dev
```