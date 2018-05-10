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

User registers an application through the accounts app, submitting this information:

* ID
* Name
* Thumbnail image
* Business name
* Support URL
* Contact email

In return they receive:

* Private app token
* Refresh token (we will not initially implement token refresh but developers should be prepared to store and use these in future)
* App ZUID (zesty unique identifier)
* Client app id (name)

### Application Requirements



# Drawbacks
[drawbacks]: #drawbacks

TODO

# Rationale and alternatives
[alternatives]: #alternatives


# Unresolved questions
[unresolved]: #unresolved-questions

TODO
