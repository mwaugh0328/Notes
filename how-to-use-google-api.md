## How to use Google APIs

I want to be able to download messages an possible manipulate my GMAIL account via python. How do you do this?
Fortunately, Google has some APIs that allow you to do this. I have still not worked everything out, not even close, but here is some stuff

---

## How to get started

First, google has a quick start cheat sheet for pyhon. The link is here:

https://developers.google.com/gmail/api/quickstart/python

And then follow the instructions. Success is if in your terminal/command prompt the folder labels associated with your GMAIL account print out.

But I want to get access to the messages. After setting up my credentials (this is the service.users part I think) then this command will generate a list of your messages.

Note to get this running, you need to create the service object using quickstart

```
test = service.users().messages().list(userId='mwaugh@stern.nyu.edu',q='from=spencerlyon2@gmail.com').execute()

```

So the code above will generate a list of messages, in this case they are from spencer. Then to get a specific message you can grab the ID associated with it...

```
test = service.users().messages().get(userId='mwaugh@stern.nyu.edu',id='15eaa1a8b4e79370').execute()

```

Now test here is a dictionary and then you can do things like

```
test['snippet']
```
which is then going to print the snippet of the code.

How to print the whole thing?????






https://developers.google.com/gmail/api/v1/reference/users/messages/get

```
message = service.users().messages().get(userId=user_id, id=msg_id,
                                         format='raw').execute()

print 'Message snippet: %s' % message['snippet']

msg_str = base64.urlsafe_b64decode(message['raw'].encode('ASCII'))

mime_msg = email.message_from_string(msg_str)

```
