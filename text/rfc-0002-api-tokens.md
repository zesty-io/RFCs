# RFC 0002 - API Tokens

## Summary

This is an RFC to propose the introduction of API tokens to Zesty.io, to allow users and third party applications to authenticate and interact with the platform in a controlled manner.

## Motivation

Reasons for adding API tokens:

* To allow developers to build external applications that can access and manipulate content inside a Zesty.io instance
* To allow developers to build external applications that can perform management functions against the Zesty.io platform such as:
  * Creation / management of instances
  * User management
* To allow developers to build extensions to the Zesty.io platform that can be integrated into existing Zesty interfaces
* To enable entirely headless operation of the Zesty.io platform

## Detailed Design

We propose to use the OAuth 2 protocol to authenticate and authorize third party applications with the Zesty.io platform.  Specifically, we propose to use the OAuth 2 Authorization Code flow (see [example tutorial from DigitalOcean](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2#grant-type-client-credentials)).

### Registration of Applications

Developers building applications that interact with Zesty.io platform will need to provide the following information to the platform:

* Application name (will be shown to user as part of OAuth 2 process)
* Application callback URL (SSL protected URL that Zesty.io will hit as part of the OAuth 2 process)

Zesty.io platform will generate and issue the following for each third party developer application:

* Client ID (to identify the application to the platform)
* Client Secret (used as part of the OAuth 2 process, should be treated as a password and not shared or put into source control)

### Authorization Tokens / Grants

We have identified the need for the follow types of token and access grants. 

#### Authorization Code

Issued by Zesty.io platform and provided to the third party application via its OAuth 2 callback URL.  Used to obtain an access token for a specific user and grant type.

#### Role to Instance Grant

A grant which enables operations permitted by a Zesty.io platform role to be performed against a specific Zesty.io instance.  The third party application will receive a token that can be used to perform any operation that the user's role allows against a specific instance on Zesty.

#### User to Platform Grant

A grant which enables operations permitted by a Zesty.io platform role to be performed against any instance that the role has access to.  This third party application will receive a token that can be used to perform any management actions associated with the role such as creation of a new instance.

### Token Lifecycle

Tokens can be:

* Created (with or without expiry dates)
* Revoked
* Expired

Tokens cannot be:

* Modified (a given token will always have the same permissions, to change those, revoke the token and issue a new one)

Tokens are:

* Universally unique
* Secrets that should not be committed to source control or shared

### Process for Issuing Tokens

* OAuth 2 authorization code flow (for server apps)

### Process for Refreshing Tokens

* We will issue refresh tokens and ensure that they have long expiry dates (our plan is to not enforce refreshing until later)
* No official refresh process at this time (May 2018)
* Developers should assume that refresh tokens will be fully implemented in future, and store these somewhere in their application

### Process for Revoking Tokens

TODO

### Third Party Application Requirements

* Third party applications wishing to authenticate with Zesty.io platform must provide an OAuth callback URL that is secured with SSL

### Implementation Examples

In addition to online documentation describing how to obtain, manage and work with the tokens, Zesty.io intends to provide at least one example project demonstrating how to interact with the platform programmatically.

## Alternatives

TODO - are there alternative approaches that we should consider?

## Unresolved Questions

TODO - what outstanding questions are there about this feature?
