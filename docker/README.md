# Docker Compose to Launch Identfy
Docker Compose file for launching an instance of Identfy for testing purposes.

The environment variable **DEVELOPER_MOCKUP_ENTITIES** is activated to avoid the need to define integration endpoints, generating empty credentials. To properly use the Wallet, it is important to integrate it with an Authentic Source. In order to do so, the Authentic Source needs to implement an API REST and the Wallet needs to know the URL the Authentic Source service is using. This URL needs to be specified using the **ENTITY_URL** variable. You can learn more about the integrations in the repository for the backend component.

## Requirements
- Docker
- Ngrok (Optional). Necessary if you want to use Ngrok as a mechanism to generate a public URL

## Quick Start
1. Define environment variables. They can be passed via the command line, but the easiest way is to copy the [.env.example](.env.example) file as .env and edit it.
2. Edit the .env file and set the public URL of the application and the DID the Wallet is going to use, for example:
   ```
   PUBLIC_URL=<PUBLIC_URL>
   DID=<DID>
   ```
3. Run
```bash
docker compose build
docker compose up
```
4. Access the public URL defined in the PUBLIC_URL variable.

## Ngrok
An easy way to generate a public URL for testing is by using [Ngrok](https://ngrok.com/). There are different ways to run Ngrok. If you have Node.js, you can run the following:
```bash
npx ngrok http 8000
```