## Instructions
- Create `.env` file from `.env.example` file
- start the container with command
```
docker compose up --build -d
```
- open `https://localhost:5678/` in browser. Ignore unsafe url error
- add admin username and password for n8n
- goto mysql database http://localhost:8081/index.php?route=/database/structure&db=hackathon_db
- create a table `email_logs` with following sql command
```
CREATE TABLE `email_logs` (
  `messageId` varchar(255) NOT NULL,
  PRIMARY KEY (`messageId`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```
- a sample workflow can be created using `test.json` file. It is listening to emails from `prabalpradhan20@gmail.com` coming to `prabal@jobins.jp`  and forwarding them to slack channel `crm-test-channel`. `prabal@jobins.jp` cannot be changed, if you want to change this you need to create a project in google console. to change `prabalpradhan20@gmail.com` change `test.json` `line:20`.

## Credentials
- gmail credentials are present in https://console.cloud.google.com/auth/clients/837224373660-b8uo0l4kkhhjs85lpefnsh2cmf66mgt9.apps.googleusercontent.com?project=n8n-integration-493807. You will need `clientID` and `client secret`
- slack credentials are present in https://api.slack.com/apps/A0AU95EHU6M/general? You will need `Signing Secret` in `Basic Information` and `Bot User OAuth Token` in `Install App` section.

