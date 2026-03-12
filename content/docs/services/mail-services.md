---
title: Mail Services (MAIL)
weight: 1
---

The Mail Services site hosts the primary e-mail infrastructure.

## Services

The mail server hosts the following components:

| Service                              | Description                         | URL                                      |
| ------------------------------------ | ----------------------------------- | ---------------------------------------- |
| **Mailcow (Postfix, Dovecot, ...)**  | Core mail transfer and delivery.    | <https://mail.muehlbachler.io>           |
| **SOGo**                             | Web-based mail client.              | <https://mail.muehlbachler.io/SOGo>      |
| **SimpleLogin**                      | Mail aliasing and privacy service.  | <https://aliases.email.muehlbachler.io>  |

## Configuration

### Outbound Mail Relay

To ensure reliable delivery and avoid spam filters, outbound mail is relayed through [DuoCircle](https://www.duocircle.com).
This setup allows for better deliverability and management of outgoing emails.

### DKIM and SPF

The mail server is configured with DKIM and SPF records to enhance email security and prevent spoofing.
DKIM is set up to sign outgoing emails, while SPF records are configured to specify authorized mail servers for the domain.

### DMARC

DMARC policies are implemented to provide instructions on how to handle emails that fail DKIM or SPF checks.
This helps in protecting the domain from unauthorized use and phishing attacks.
