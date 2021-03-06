An action that simply sends a mail to multiple recipients.

## Usage

```yaml
- name: email-bot
  uses: rajsh018/email-bot@v1
  with:
    # Required mail server address:
    server_address: smtp.gmail.com
    # Required mail server port:
    server_port: 465
    # Optional (recommended): mail server username:
    username: ${{secrets.MAIL_USERNAME}}
    # Optional (recommended) mail server password:
    password: ${{secrets.MAIL_PASSWORD}}
    # Required mail subject:
    subject: Github Actions job result
    # Required recipients' addresses:
    to:  ${{secrets.USER_EMAILS}} #user1@example.com,user2@example.com
    # Required sender full name (address can be skipped):
    from: User Action # <user@example.com>
    # Optional whether this connection use TLS (default is true if server_port is 465)
    secure: true
    # Optional plain body:
    body: Build job of ${{github.repository}} completed successfully!
    # Optional priority: 'high', 'normal' (default) or 'low'
    priority: low
```
