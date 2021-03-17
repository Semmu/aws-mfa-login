# `aws-mfa-login`

Simple shell script to login to AWS on the CLI with an MFA token.


## Installation

* `git clone` this repository where you'd like.
* Add `aws-mfa-login` to your `$PATH`, e.g

  `sudo mv aws-mfa-login /usr/local/bin`


## "Configuration"

The first time you run `aws-mfa-login` it is going to ask for your MFA device's ARN identifier, which will be stored in `~/.aws/mfa-arn` and used afterwards.

Also, if you haven't configured `aws` yet, it will force you to do it as well by running `aws configure`.


## Usage

Run the script and pass your current MFA token as a parameter, e.g.

```bash
aws-mfa-login 123456
```

It will start a _**subshell**_ for you where the temporary access credentials are set as _environment variables_. From that point on `aws` commands should work as expected.

You can validate that it set the environment variables by running `env | grep AWS`.


## License

MIT
