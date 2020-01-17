## Working within the system

What is the smallest step that moves the web towards adopting a system of decentralized identifiers.
Building a Self-Issued OpenID Connect Provider (SIOP) in the browser.

### The Auth protocols of today

The standard for authentication and authorization today is OAuth 2.0 and the Open ID Connect (OIDC) extension.
These are used by many applications on the web today, including social login.

The fact these protocols have been used over several years and in many applications shows that they are useful.
Their continued existence demonstrates that the are sufficiently secure for many usecases.
Developers understand them, or at least how to use them in their ecosystem of choice.

Even more importantly developers know to look for these protocols.
The majority may not care about about the details, e.g. why OAuth 1.0 got replaced with OAuth 2.0,
However, they do understand how make use of them to solve Authentication and Authorization in their applications.

So familiarity is the strength of these existing protocols.
A downside is, in today's world, they are often used to further centralize the web.
In fact social logins is a contract that few understand but which greatly extends the reach of these companies to follow their customers around the internet.

## The Auth protocols of tomorrow

What if the privacy respecting applications of tomorrow also used these protocols.
Their would be less wheels to reinvent and adoption would be closer.

Specifically using OIDC to fetch a decentralized identity would enable of all the connecting infrastructure that exists today.
Most ecosystems have OAuth and OIDC integrations.

So is it possible to build a, compelling, decentralized Identity Provider.
To be compelling it must compromise neither security or convenience of the existing solutions.

## Self-Issued OpenID Provider

The OIDC specification supports the idea of a Self-Issued OpenID Provider (SIOP)[1].
Theoretically, therefore, the ability to issued decentralized identities exists within the current protocols.
Practically there are very few that use such a decentralized.

## Best practises required

The application that makes use of the identity from an OpenID Provider is the Relaying Party.
A key reason why a Relaying Party might offload it's authentication to an OpenID Provider is so they can delegate, some of, their security concerns to that service

When switching to a SIOP some of the security concerns, that were previously delegated, switch back to being the responsibility of the RP.
For example:

- email verification, a SIOP can add the claim of email and email_verified but their is no entity validating this to be true for that id.
- spam accounts, a SIOP can issues as many identities as they want, their is no rate limiting.
- account recovery, what happens if a key is lost, is the identity lost with it?

I believe these problems hold back the adoption of SIOP's but that only small changes are needed to make their use compelling.
Many of these problems are familiar to other decentralized applications:

For example an email provider could issue a claim to the SIOP that says it has an email with the provider.
The SIOP can now use this claim to authenticate with an RP, but without the email provider knowing which RP was visited or when.

This usecase doesn't require a fully fledged Decentralized ID (DID) ecosystem.
The email provider can be identified via DNS and the record of it's public signing keys kepts at the `jwks_uri` endpoint that is already in existence as part of the OpenID configuration.

Can we do this with small changes. (TODO this line)

## Goals

Discuss what would need to exist for businesses to add a Self-Issued OpenID Provider to the OAuth options they already support.
Having a button to select self issue next the login with Facebook/Google buttons would at least offer another option

- What service could provided verified claims that make a SIOP useful.
- Can a secure SIOP be built in the browser?
- How does a SIOP have claims added to it?
- What organisation should host it?
- Do existing libraries support self issued part of the OIDC spec.
- How do end users upgrade their SIOP to one of their own preference, for example on that creates a new identity for every Relaying Party.

(1) https://openid.net/specs/openid-connect-core-1_0.html#SelfIssued
