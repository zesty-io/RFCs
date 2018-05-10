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

### Types of Token

We have identified the need for the follow types of access token.

#### Application Token

Authenticates applications to the Zesty.io platform.  Permits applications to authenticate Zesty.io users and obtain tokens to perform actions on their behalf.

#### Role to Instance Token

A token which enables operations permitted by a Zesty.io platform role to be performed against a specific Zesty.io instance. 

#### User to Platform Token

A token which enables operations permitted by a Zesty.io platform role to be performed against any instance that the role has access to.  Includes any management actions associated with the role such as creation of a new instance.

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

TODO

### Process for Refreshing Tokens

TODO

### Process for Revoking Tokens

TODO

### Implementation Examples

In addition to online documentation describing how to obtain, manage and work with the tokens, Zesty.io intends to provide at least one example project demonstrating how to interact with the platform programmatically.

## Alternatives

TODO - are there alternative approaches that we should consider?

## Unresolved Questions

TODO - what outstanding questions are there about this feature?
