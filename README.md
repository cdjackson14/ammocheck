# AmmoCheck

This checks several online sources for availability of 9mm ammo, then emails out the result.

This was originally created in 2020 when ammo became hard to find in stock.

## Required Items

* curl  - Normally already installed, if not see below
* sSMTP - https://wiki.debian.org/sSMTP

----------

## sSMTP

### Installation

```bash
sudo apt install ssmtp
```

### Configuration

1. Edit `/etc/ssmtp/ssmtp.conf`

    > Special Note:  If using Gmail, use an app specific password.  Find out how and why at https://support.google.com/mail/answer/185833?hl=en-GB

    Example for using Gmail:

    ```
    root=<gmail_address>
    mailhub=smtp.gmail.com:587
    hostname=localhost
    FromLineOverride=YES
    AuthUser=<gmail_address>
    AuthPass=<something secret created by Google>
    UseTLS=yes
    UseSTARTTLS=yes
    ```

2. Edit `/etc/ssmtp/revaliases`

    ```
    root:<gmail_address>:smtp.gmail.com:587
    ```

### Optional Crontab Config
By default, the crontab will send email to the local username, sSMTP will mess this up, and try sending to an invalid email, and all crontab notification will be rejected.  Here's a simple solution.

Add the MAILTO line at the top of the crontab

```
MAILTO=<gmail_address>
```

done

