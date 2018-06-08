Good practices
===============

Here are a few suggestions on good practices while using computers daily life.
In this guide we mentioned a few major habits or tools., and then we also
links to documents to learn more about those habits or tools.

Use strong and unique passwords
-------------------------------

We should use unique passwords in different places. Otherwise, if someone can
get hold of one of your password, they can break into other sites/places with
the same password. We suggest using `diceware
<https://github.com/ulif/diceware>`_ to generate all of your passwords. To
learn more, please read `this blog post
<https://kushaldas.in/posts/using-diceware-to-generate-passwords.html>`_.


Use password managers
-----------------------

Password managers will help you to store all of those long passphrases in one
place. Learn from this guide about `password managers
<https://medium.com/@mshelton/password-managers-for-beginners-d1f49866f80f>`_.
`KeePassXC <https://medium.com/@mshelton/keypass-for-beginners-dc8adfcdad54>`_ is a good option on desktop.


Do not keep the computer unlocked
----------------------------------

If you are not in front of the computer, then always lock the screen. Do not
keep the computer unlocked, let it be inside your house, or in your hostel, or
in anywhere else. This is again an habit, and it takes time to make this
habit. Having the computer always password protected will make sure that any
person can not directly access your computer even if you are not front of the
computer for few minutes.

Cover up your webcam
---------------------

Over the last few years it became very well known that big agencies and
criminals can access people's webcams and record without anyone knowing.
Covering up your laptop webcam will protect you at one level against these
criminal activities. Here is `story
<http://thehill.com/policy/national-security/295933-fbi-director-cover-up-your-webcam>`_
which talks about how the FBI director also puts up a tape on his laptop's
webcam.

Keep your machine updated
--------------------------

Always keep all the software updated. There are always new security updates
available, and we should install them as soon as possible. This is true not
only for normal computers, but, also for mobile phones and any other modern
smart home internet things.

Take regular backups
---------------------

One should always backup their computer, and if possible more than one backup
copy. For example, you should at least backup your ssh keys, gpg keys, and all
other important configs in couple of **encrypted usb drives**.

.. note:: Learn how to encrypt your USB drives below


Enable 2 factor authentication
-------------------------------

Enable 2 factor authentication in all the websites or applications (if they
allow it). This will provide a second layer of security incase someone finds
your password.

If possible also stay away from SMS based 2 factor authentication. Instead,
use the mobile applications like **FreeOTP**, **Google Authenticator**,
**Authy**. These generates time based tokens which can be used as 2FA.

To know more which all sites provides 2 factor authentication, visit
`https://twofactorauth.org <https://twofactorauth.org>`_.

Encrypt all USB drives
------------------------

While installing Linux in your system, you can encrypt the whole drive. This
will help in case your laptop is stolen or taken away by someone. This also means
try to keep your laptop in shutdown state most of the time, so that to boot the system,
one will have to provide the encryption password.

The same goes to the all USB devices you use. We have much bigger chance to
misplace or forget about small USB devices. `How to encrypt USB devices using
LUKS <https://kushaldas.in/posts/encrypting-drives-with-luks.html>`_ has all
the details you need to know to encrypt or decrypt any USB device.
