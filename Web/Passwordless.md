# Passwordless

**Category: WEB**

**Description:**

>Tired of storing passwords? No worries! This super secure website is passwordless!

### Solving the challenge

```py
#!/usr/bin/env python3
from flask import Flask, request, redirect, render_template, render_template_string
import subprocess
import urllib
import uuid
global leet

app = Flask(__name__)
flag = open('/flag.txt').read()
leet=uuid.UUID('13371337-1337-1337-1337-133713371337')

@app.route('/',methods=['GET','POST'])
def main():
    global username
    if request.method == 'GET':
        return render_template('index.html')
    elif request.method == 'POST':
        username = request.values['username']
        if username == 'admin123':
            return 'Stop trying to act like you are the admin!'
        uid = uuid.uuid5(leet,username) # super secure!
        return redirect(f'/{uid}')

@app.route('/<uid>')
def user_page(uid):
    if uid != str(uuid.uuid5(leet,'admin123')):
        return f'Welcome! No flag for you :('
    else:
        return flag

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=1337)
```

After taking a look to the code we can see that we have a UUID generated using variable **leet** which is **uuid.UUID('13371337-1337-1337-1337-133713371337')** and the string **admin123**.

I did this locally using python IDLE :

```py
>>> import uuid
>>> leet=uuid.UUID('13371337-1337-1337-1337-133713371337')
>>> uid = uuid.uuid5(leet,"admin123")
>>> uid
UUID('3c68e6cc-15a7-59d4-823c-e7563bbb326c')
```

Using this UUID on the website we have the flag !

![Result](/images/Passwordless.JPG)


### Flag

```n00bz{1337-13371337-1337-133713371337-1337}```
