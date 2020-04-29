# Fail2ban Telegram Notifications

![](https://deividsdocs.files.wordpress.com/2020/04/telegram_notifications_fail2ban.jpg)

Sending **fail2ban** notifications using a **Telegram** bot

## Installation and configuration
- Add the following two lines, for example, to **SSHD** in the file **/etc/fail2ban/jail.conf**, make sure to tab the word **telegram**.
  
  `action  = iptables[name=SSH, port=22, protocol=tcp]`
	
  `		telegram`
  
  ![](https://deividsdocs.files.wordpress.com/2020/04/fail2ban-sshd-conf.png)
  
- Download the file **telegram.conf** and move it to **/etc/fail2ban/action.d/**
- Download the file **send_telegram_notif.sh** move it to **/etc/fail2ban/scripts/**
- Modify the file **/etc/fail2ban/scripts/send_telegram_notif.sh** and add your **Token** and your **Chat ID**:

  `telegramBotToken=YOUR_BOT_TOKEN`

  `telegramChatID=YOUR_CHAT_ID`
- Make the file executable

  `chmod +x /etc/fail2ban/scripts/end_telegram_notif.sh`
- Restart the fail2ban service and enjoy!

  `systemctl restart fail2ban`
 
## Usage
+ /etc/fail2ban/scripts/send_telegram_notif.sh -a ( start || stop ) || -b $IP || -u $IP"
  + -a (action)
  + -b (ban)
  + -u (unban)
  
## Buy me a coffe
[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/U7U01LTQB)

