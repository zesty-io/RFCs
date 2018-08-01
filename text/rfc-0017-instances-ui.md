# RFC 0017 - Instances UI

Instances UI is the front-end application for managing an instance created with the Zesty.io CMS. It provides instances members interface to do CRUD operations against content, code, schemas and media. As well as supporting operations such as; managing form submission, analytics, route management, instance settings, etc...

## Summary

Our goal is to piece meal port portions of the UI to a modern front-end stack. By categorizing each "tab" or distinct management section of the existing into a "sub-app" we can one by one rebuild them. Thus avoiding the typically catastrophic complete application rebuild. Ultimately our end goal is to have a complete rebuild which implements all of the UI with a component architecture. As well as including modern sophisticated technologies of service workers, offline, caching. i.e. A Progressive Web Application

## Motivation

Currently our application uses internally developed solutions for building UI. This creates barriers to entry for new hires and contributors. By adopting a new tech stack that fits with modern technologies and architectures we'll create a codebase that allows developers to ramp up faster and deliver a codebase which allows us to iterate faster thus being able to respond to customer needs quicker.

There are a myriad of secondary benefits that we will gain as well, such as; shipping small bundles, taking advantage of tooling built to work with these newer technologies, the crowd benefits of adopting open source solutions, taking advantage of prebuilt solutions for many UI problems we'd traditional need to developer ourselves.
