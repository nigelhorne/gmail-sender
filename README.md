# Gmail Sender Script

This script sends an email using Gmail’s SMTP server (`smtp.gmail.com`).  
It reads the email body from a file and supports authentication either via command-line arguments or a configuration file in your home directory.

## Requirements

Install the required modules using CPAN:

```sh
cpan Email::Sender::Simple \
     Email::Sender::Transport::SMTP::TLS \
     Email::Simple \
     Email::Simple::Creator \
     Getopt::Long
````

## Usage

```sh
perl send_gmail \
  --from     'your.name@gmail.com' \
  --to       'recipient@example.com' \
  --subject  'Hello World' \
  --file     message.txt \
  --username 'your.name@gmail.com' \
  --password 'your-app-password'
```

If you omit the `--username` and `--password` options, the script will attempt to read them from a configuration file.

## Configuration File

Create a file at:

```
$HOME/.conf/gmail-sender
```

And add the following content:

```
username=your.name@gmail.com
password=your-app-password
```

> **Important**: Use a Gmail **App Password** instead of your real Gmail password.
> You can create one by visiting your [Google Account settings](https://myaccount.google.com/)
> and navigating to **Security → App passwords**.

## Licence

Personal single user, single computer use: GPL2

All other users (including Commercial, Charity, Educational, Government)
  must apply in writing for a licence for use from Nigel Horne at the
  above e-mail.
