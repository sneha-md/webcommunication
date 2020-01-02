## slack package
###### slack package contains two modules: `slackchannel` and `slackmessage`.
### slackchannel.py
-This module uses Slack API (Application Programming Interface), which is used to communicate Slack with Python
- Using `slackchannel` module, the user can establish a connection with Slack and create a private channel using Python.
-This module has one class  `slackChannel` with two functions `connection` and `createchannel`.
-This module uses `import slack` to access Slack from Python.

`connection` function is used to create a connection with Slack before creating a channel.
* This module uses a slack function `WebClient`, which has parameters that needs to be passed in order to connect Slack with Python. The user will pass a token (the token can be generated from Slack API) to establish a connection.

`createchannel` function helps the user can create a private channel once a connection has been made.
* This function has one parameter, which is the name of the channel.
-When this is called, it automatically connects the user and creates a private channel.
-Slack function `groups_create` creates a private channel for the user.

### slackmessage.py
- Using `slackmessage` module, the user can send a message in any channel.
- This module has two classes `slackConnect` and `slackMessage(slackConnect))` and three functions `connection`, `sendmessage`, and `scheduledmessage`.
-This module has the following modules: `import slack`, `import calendar`, `import datetime`, and `import timedelta`. Since Slack uses UNIX timestamp these modules are used to convert PST time to UNIX timestamp.

 `slackConnect`, is a super class. `slackMessage` is inherited from `slackConnect` class.
* Using `sendmessage` function, the user can input channel name, a text message, and preferred username (default is "Slack API tester")
  - Slack function `chat_postMessage` is used to send message in the user created channel.
-Using `scheduledmessage` function, the user can input channel name, a text message, and date in *yyyy-mm-ss hh-mm-ss* format.
  - Slack function `chat_scheduleMessage` is used to send message in the user created channel at a chosen time.
