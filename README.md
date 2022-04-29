# SAML to AWS STS Keys Conversion
The legendary Chrome extension for SAML to AWS CLI credentials forked. PEA (Packaged Enterprise Application) variation will feature 
* Latest library [from cdnjs](https://cdnjs.com/libraries/aws-sdk) 
* Automatic backup and insertion of credentials into your `~/.aws/config`

Google Chrome Extension which converts a SAML 2.0 assertion to AWS STS Keys (temporary credentials). Just log in to the AWS Web Management Console using your SAML IDP and the Chrome Extension will fetch the SAML Assertion from the HTTP request. The SAML Assertion is then used to call the assumeRoleWithSAML API to create the temporary credentials. (AccessKeyId, SecretAccessKey and SessionToken).

# TODO 
* Ensure plugin to be plug and play on Windows, Linux, and Mac.
* Make a developer manual on this, so that everyone can tinker with this thing.


# Table of Contents
* [Why this Chrome Extension?](#why)
* [Getting Started](#gettingstarted)
* [Create a symlink to your .aws directory (for Windows users)](#symlink)
* [Frequently Asked Question](#faq)

## <a name="why"></a>Why this Chrome Extension?
If you don't have any user administration setup within AWS Identity & Access Management (IAM) but instead rely on your corporate user directory, i.e. Microsoft Active Directory. Your company uses a SAML 2.0 Identity Provider (IDP) to log in to the AWS Web Management Console (Single Sign On). Then this Chrome Estension if for you!

You run into trouble as soon as you would like to execute some fancy scripts from your computer which calls the AWS API's. When sending a request to the AWS API's you need credentials, meaning an AccessKey and SecretKey. You can easily generate these keys for each user in AWS IAM. However, since you don't have any users in AWS IAM and don't want to create users just for the sake of having an AccessKey and SecretKey you are screwed. But there is a way to get temporary credentials specifically for your corporate identity.

The Security Token Service (STS) from AWS provides an API action assumeRoleWithSAML. Using the SAML Assertion given by your IDP the Chrome Extension will call this API action to fetch temporary credentials. (AccessKeyId, SecretAccessKey and SessionToken). This way there is no need to create some sort of anonymous user in AWS IAM used for executing scripts. This would be a real security nightmare, since it won't be possible to audit who did what. This Chrome Extension however will make it super easy for you to just use your corporate identity for executing scripts calling AWS API's.

## <a name="gettingstarted"></a>Getting Started
TODO

## <a name="symlink"></a>Create a symlink to your .aws directory (for Windows users)
TODO

## <a name="faq"></a>FAQ: Frequently Asked Question
1. Why can I not save file somewhere else?
TODO
2. How long are the credentials valid?
