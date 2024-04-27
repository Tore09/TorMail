## Installation

Install the package with: `pip install tormail`

## Example
```python
import tormail
import json

mail = tormail.MailClient()

generated_mail = mail.register()

print(f"""
Mail created

Mail: {generated_mail["address"]}
Pass: {generated_mail["password"]}
""")

def listener(message):
    message_content = json.loads(message)
    subject = message_content["subject"]
    content = message_content["content"]
    
    print(subject)
    print(content)

mail.start_listening(listener=listener)
```
### Output
```text
Mail created

Mail: hekz852pmnuplb5@fthcapital.com
Pass: W+[#6tACP4
```
### On Mail Received
```text
Subject from incoming mail!
This is the content from an incoming mail!
```



## Features
### Register
`MailClient.register()`

Parameters
```
username | optional
password | optional
```

### Start Listening
`MailClient.start_listening()`

Parameters
```
listener | required
interval | optional
```

### Stop Listening
`MailClient.stop_listening()`

Parameters

`None`
