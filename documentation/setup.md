# Setup

> <p><span style="color:red"><em>Warning #1: While you can use free-tier AWS services as much as possible to deploy CloudGoat scenarios, you can expect some minimal account charges</em></span>.</p>

> <p><span style="color:red"><em>Warning #2: CloudGoat creates intentionally vulnerable AWS resources into your account. DO NOT deploy CloudGoat in a production environment or alongside any sensitive AWS resources.</em></span>.</p>
> <p><span style="color:red"><em>Warning #3: CloudGoat can only manage resources it creates. If you create any resources yourself in the course of a scenario, you should remove them manually before running the destroy command.</em></span>.</p>


## Create an AWS account

One of the prerequisites to deploy CloudGoat scenarios is a working and payment enabled AWS account. 

You can follow the AWS documentation to create and activate an AWS account https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/

## Create an IAM user 

When you first create an Amazon Web Services (AWS) account, you begin with a single AWS account root user that has complete access to all AWS services and resources in the account. 

As a best practice, do not use the AWS account root user for any task where it's not required. Instead, create IAM users with appropriate permissions.

For CloudGoat, we need to deploy various resources across services in our AWS account. For this purpose it is handy to create an IAM user with Adminstrator access.

You can follow our documentation to create an IAM user with Adminstrator access https://github.com/appsecco/breaking-and-pwning-apps-and-servers-aws-azure-training/blob/master/documentation/setting-up/creating-an-iam-admin-user.md

## Configure your profile using AWS CLI

A "named profile" is a collection of settings and credentials that you can apply to an AWS CLI command. CloudGoat needs an AWS profile to work with. You can configure an AWS profile using [AWS CLI](https://aws.amazon.com/cli/), official AWS tool to manage your AWS services.

You can follow the AWS documentation to install AWS CLI on Linux/macOS https://docs.aws.amazon.com/cli/latest/userguide/install-cliv1.html

Run the following command to configure a profile named "cloudgoat"

        aws configure --profile cloudgoat

You will need to provide the `access key ID` and `secret access key` of the IAM user, which you have saved earlier

Type the following values

Default region name [None]: `us-east-1`

Default output format [None]: `json`

These credentials get stored in the file at  `~/.aws/credentials`

Run the following command to confirm if you are setup or not. This command should show your Account ID

    aws sts get-caller-identity --profile cloudgoat

## Setting up CloudGoat

You can setup and configure CloudGoat using the instructions available at https://github.com/RhinoSecurityLabs/cloudgoat/#requirements


## Additional information

- [Named Profiles](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html)