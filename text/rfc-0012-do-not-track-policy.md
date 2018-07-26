# RFC 0012 - Do Not Track (DNT) Policy in Zesty.io

## Summary

The electronic frontier foundation put out a spec to tell ad blockers what sites to trust, more can be  read here https://www.eff.org/issues/do-not-track. For W3C policies visit https://www.w3.org/TR/tracking-dnt/. Setting this up requires some configuration to response bodies and creation of files in the .well-known path of a domain.

## Motivation

DNT policies should be readily available for anyone who publishes to the internet.

## Detailed Design

* allow `/.well-known/dnt-policy.txt` file
* create setting option to append the header `DNT: 1` to all get requests

## Details

See how to implement this on Zesty.io https://www.youtube.com/watch?v=7BUjD3piGW4
