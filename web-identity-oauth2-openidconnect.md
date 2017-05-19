## Web identity: OAuth2 and OpenIDConnect

speaker: Brendan McCollam
time: Friday 12:10 am - 12:40 pm
[description](https://us.pycon.org/2017/schedule/presentation/276/)
[slides and code](http://brendan.mccoll.am/pycon2017/)

- Web Identity (avoid pedantics - OAuth, SSO, etc.)

## Why would you want that?

- Convenience
- Platform
- Security
- Sheer laziness

## Semantic differences

- Authorization Protocol - like a key
    - OAuth 2.0

- Authentication Protocols - like an ID badge
    - OpenIDConnect (extends OAuth 2.0)

## OAuth 2.0

- How do you let users log in without seeing their passowrds?
- RFC 6749
    - `access_token`: our "key"
    - `scope`: "what the key unlocks"
    - A "framework", not a specification

## Authorization Code Grant

## OpenID Connect

- Set of extensions to OAuth2
- Adds the missing authentication layer
- Enabled via special "openid" scope
- Returns id_token
    - JSON Web Token (JWT)
    - contains "claims"
        - given_name
        - email
        - address
        - Whatever else the authentication server looks like

