
**Simple Mail Transfer Protocol**

It is an application layer protocol used to send and receive emails. It is a push protocol whereas HTTP is a pull protocol. A user agent/mail client (could be Outlook or Webapp) forwards message to the sender's mail server. The sender's mail server adds the e-mail to a queue and then the sender's mail server forwards the mail to the recipient's mail server. When the recipient opens his mail client, the client retrieves the email sent to him from its own mail server.

The recipient's mail server does not use SMTP to forward the mail to the client instead it uses another protocol. There are two protocols to fetch emails from the mail server namely POP3 and IMAP (Internet Mail Access Protocol). Modern email clients now use HTTP to send and receive emails but the mail servers still use SMTP to forwards messages between the mail servers