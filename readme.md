# Description

Due to the requirements of the serv00 server, if the user account is not correctly logged in through DevilWEB or SSH panel within 90 days, the account will be automatically deleted from the system and the data collected by the account cannot be recovered.

This repository will be used to automatically log in to the SSH connection of serv00 at a scheduled time to execute instructions and push notifications, which can achieve the role of regular login to keep the account

### Preparation

- A GitHub account.
- Fork this repository
- Prepare a serv00 account
- Get the Chat ID of your Telegram user or group.

- Set the following Secrets in your GitHub repository:

### Configure Secrets

- Go to your own repository page after forking this repository > "Settings" > "Secrets" and add the following Secrets:

- `SSH_INFO`: A JSON string containing SSH connection information. The following is an example

```json
[
{"hostname": "Server number", "username": "User name", "password": "Password"},
{"hostname": "s5.serv00.com", "username": "user", "password": "password"},
{"hostname": "s6.serv00.com", "username": "user6", "password": "password6"}
]
```
- ~PUSHPLUS_TOKEN: token applied by pushplus~
- **The new version has removed pushplus push, please do not add PUSHPLUS_TOKEN variable**
- **The new version has removed pushplus push, please do not add PUSHPLUS_TOKEN variable**
- **The new version has removed pushplus push, please do not add PUSHPLUS_TOKEN variable**
- TELEGRAM_BOT_TOKEN: Your Telegram Bot API Token. Example: `733255939:AAHsoQf-3lOoc1xC8le2d58qlfrCqEXzu74`
- TELEGRAM_CHAT_ID: Your Telegram Chat ID (can be your private chat or group). Example: `5329499650`
- PUSH: Push channel value is `mail` or `telegram`. Example: `mail`
- MAIL: Email address to receive notifications. Example: `mail@mail.com`

### Test run

- Manually trigger a workflow run in the Actions tab of the GitHub repository.
- "Actions" page>"Run SSH Login">"Run workflow">"Run workflow"
- Check the running results. If there is no error, it means the running is successful. You can click the list of running records to view the running details

### Scheduled automatic running

- This workflow runs at 19:00 Beijing time on the 5th of each month by default

- You can adjust the running time according to your needs

```yaml
- cron: '0 11 5 * *' # Run at 19:00 Beijing time on the 5th of each month
```

### Notes

- **Confidentiality**: Secrets are sensitive information, please make sure not to disclose them to public code bases or unauthorized personnel.
- **Update and delete**: If you need to update or delete Secrets, you can manage them through the Secrets page of the repository.

With the above steps, you can successfully fork the code to your repository and run it. If you need further help or have other questions, please feel free to let me know!
