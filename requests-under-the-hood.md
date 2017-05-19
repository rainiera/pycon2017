## Requests Under The Hood

speaker: Cory Benfield  
time: Friday 10:50 am - 11:20 am  
[description](https://us.pycon.org/2017/schedule/presentation/71/)

- one of 4 co-maintainers of Python requests
- maintainer of urllib3

## Should I use a proxy?

- strange for unusual network topologies - like at enterprises
- requests in the corporate network wouldn't go through a proxy
- standard in UNIX; environment variables - "NOPROXY"
    - parse an awkward comma-separated list of hosts (IPs, names, etc.)
    - "follow the curl spec"
- requests
    - lots of if statements and branching
    - [here](https://github.com/kennethreitz/requests/blob/216aee441def9564698c3c186a4fcda76c218ad8/requests/utils.py#L642)
    - no tests bc it solved problems incrementally then got complicated

## How Do I Know If I Have IPv6 Support?

- `SOCKET_HAS_IPV6`
- [here](https://github.com/kennethreitz/requests/blob/e3f89bf23c53b98593e4248054661472aacac820/requests/packages/urllib3/util/connection.py#L107)
- `except Exception` - just silences

## How Long Is This File?

- File-like objects in Python aren't really a thing - "has a read method"
- [here](https://github.com/kennethreitz/requests/blob/216aee441def9564698c3c186a4fcda76c218ad8/requests/utils.py#L99)
- `fstat`
- `tell`
- `seek`

## Redirects

- [here](https://github.com/kennethreitz/requests/blob/eae38b8d131e8b51c3daf3583e69879d1c02f9a4/requests/sessions.py#L116)
- evolves to balance concerns like browsers, new specs, etc.

