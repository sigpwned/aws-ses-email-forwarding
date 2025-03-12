# aws-ses-email-forwarding

This is a simple CloudFormation template to help you set up email forwarding using AWS SES. It creates a Lambda function that forwards emails from a given domain set up for SES email receiving (e.g., `@source.com`) to another given domain (e.g., `@target.com`). After setup, SES forward emails for `john.doe@source.com` to `john.doe@target.com`.

## Setup

To use this template, you need to have the following:

1. An AWS account
2. A domain set up for SES email receiving
3. An active ruleset with an S3 action archiving emails to an S3 bucket

To set up the email forwarding, follow these steps:

1. Deploy the CloudFormation template
2. Add a rule to the SES ruleset to invoke the Lambda function *after* the S3 action

That's it! The Lambda function will forward emails from the source domain to the target domain.

## Sandbox mode

In theory, you could use this while SES is in Sandbox mode, as long as you verify the sender and all possible recipients. In practice, it's probably best to use this in a production environment.

## Disclaimer

I have successfully deployed this template to forward non-mission critical emails from one domain to another to assist with administrative tasks. If you need "real" email forwarding for day-to-day use, I highly recommend [ImprovMX](https://improvmx.com/). I use it for my business email, and it's been great.


