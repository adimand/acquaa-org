## Email

We use [SendGrid](https://sendgrid.com/) as our third-party SMTP service. This allows us to have a reliable SMTP service, track delivery, open rates etc.

![Basic SMTP Flow](https://twilio-cms-prod.s3.amazonaws.com/original_images/MailFlow.png)
Image from the [SendGrid page describing email flow.](https://docs.sendgrid.com/ui/sending-email/email-flow)

When you onboard Acquaa, we recommend that you verify your domain with SendGrid (see [this](https://docs.sendgrid.com/ui/account-and-settings/how-to-set-up-domain-authentication) page for more details). Domain Authentication is essential to ensuring the deliverability of your email and signals trustworthiness to email inbox providers and recipients. Once done, we'll be able to send emails from addresses in your domain. For e.g., you could use `bpa-support@company.com` for the BPA module or `fh-support@company.com` for the Fire Hydrant module.

