# RFC 0003 - Embedded 3rd Party Interfaces

## Summary

Extension from RFC0001. Zesty.io needs a way for a 3rd Party UI to be loaded inside of the instance manager application.

## Motivation

To allow for extensibility of our SaaS API, we need a way for developers to extend our interface to work both with our APIs and their custom build 3rd party solutions. The ability to do this drives towards an open 3rd party marketplace that will customers and developers ways to solve problems outside of our core offering.

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

TODO

# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

### Registering an Application (getting a token)

User registers and an application through the accounts app, submitting this information.

* id
* named
* thumbnail
* business name
* support URL
* contact email

In return they receive

* private app token
* refresh token
* App ZUID (zesty unique identifier)
* client app id (name)

### Loading an Application

Applications must have their source code in a single javascript file, the link to that file must be submitted (could be github or any CDN).

* Only a single JS file
* CSS and HTML should be generated in the JS
* If the app is approved, a pull request can be made against our public repository

### Submitting Application to App Store

User submits for application approval into the 3rd party app store. This calls for Zesty.io team review. Approval means all Zesty.io instances would have access to "install" the app to their respective instance and have access to the 3r party app through the content manager UI.


# Drawbacks
[drawbacks]: #drawbacks

TODO

# Rationale and alternatives
[alternatives]: #alternatives


# Unresolved questions
[unresolved]: #unresolved-questions

TODO
