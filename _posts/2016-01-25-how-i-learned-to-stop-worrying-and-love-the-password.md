---
layout: post
title: How I learned to Stop Worrying and Love the Password
categories:
- linux
- pgp
- gpg
- pass
tags: []
---

Passwords are [adjective here]. Everyone has a good story about them.


Where do you keep yours? How many can you remember? These are just some questions that many people would be embarrassed to answer publicly. And they have good reason, for we are all a part of this password protected experiment and have gone through the same tribulations.


So, you’re telling me there’s a way to be confident about passwords?


Yes and no.


There’s something user friendly in the works, and if you are adept at the terminal then join the party! If you don’t know what the terminal is and are still scared, then take a chill pill and use pen and paper for your passwords. We’re about to hack the matrix over here. I’ll try to explain when necessary, please let me know if anything is unclear.


We are using PGP keys for authentication. What this means is, a public key to share with other people, and a private key that only I (or you) have access to. These keys are plain text and can be written down or emailed. Ideally, we are actively using a subkey of a master key that is securely locked away. For optimal security, the private subkey exists only a smartcard from which it cannot be extracted, solely read internally for authentication. For optimal privacy, the setup should be performed on an air-gapped machine with a free OS.


The software we use for our PGP keys is Gnu Privacy Guard (GPG), a free implementation of the Open PGP standard.


## Enough about the keys, what about the passwords?

All in time. There is still some philosophy to be learned.


These keys vastly simplify access control management. With a collection of public keys, anyone can share secrets with one another, and only the intended recipient(s) will be able to read the message. Similarly, we can encrypt files for ourselves that only our private key can unlock.


So you could store all your passwords in a text file that only you can read. I’m sure many people do something like this (also unencrypted). But this sounds rather inefficient and clumsy. What I am proposing here is to use [password-store (pass)](http://www.passwordstore.org/).


Pass is simply a wrapper around GPG and Git. A version controlled set of directories containing pgp encrypted files. Easy to keep in sync and share, and no worries about anyone using your passwords because only you have the private key!


Keep it secret, keep it safe!
