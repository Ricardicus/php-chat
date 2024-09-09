# Chat-PGP

Welcome to chat PGP. This is an encrypted chat platform based on [PGP](https://en.wikipedia.org/wiki/Pretty_Good_Privacy).

The idea is to create a simple chat platform that is based on strong encryption. 

## Encryption

Each chat session is encrypted using a symmectrical ChaCha20Poly1305 algorithm
with a shared secret that is protected with PGP assymetrical
encryption. If you are unfamiliar with OpenPGP and using GnuPG then see this [GnuPG guide](https://www.gnupg.org/gph/en/manual/c14.html). 

## Communication

The communication protocol is built on [Zenoh](https://github.com/eclipse-zenoh/zenoh).

Zenoh is an extremely flexible middleware that does not force a network topology onto
the project. By providing a configuration file to zenoh, one can configure an entire network
of routers oneself; so that one does not have to rely on routers and peers someone else setup for
this project. Right now the router program is Zenohs standsrd daemon "zenohd". There is support for TLS (one- and two-way) authentication in zenoh. The default behaviour is desrocbed in the file zenoh/config.json5 . 

## Work in progress

This is a work in progress. So far I have this:

- PGP assymetrical encryption using pre-existing pgp-keys (you can create them with gpg)
- Communcations based on Zenoh
- Encrypted one-to-one online chat in terminal (ncurses) interface.

Will work on this:

- Better terminal interface (ncurses) in the near term
- Web front end (on localhost) in the long term
- Apply local gpg keychain as policy for session key verification
- PGP session key signed by main key instead of using the main key for each session establishment

Please feel free to test and come with feedback. This project is in its early stage
and I would appreciate contributions if you agree with this vision.

