---
id: fb8HGJXL4ovFz8JWyjGLJ
title: Time Based Otp
desc: ''
updated: 1636408631866
created: 1636397839163
---
# Time-based One-Time Passwords app (TOTP)

ref: [brycewray](https://www.brycewray.com/posts/2021/09/taming-time-based-one-time-passwords-totps/)

a method to manage your online security: [multi-factor authentication (MFA)](https://www.nist.gov/itl/applied-cybersecurity/tig/back-basics-multi-factor-authentication), which is also sometimes called two-factor authentication (2FA)

OTP is a password (usually a set of digits rather than an actual word or phrase) that is valid only once. 

time-based OTP is generated through an algorithm that computes a (usually) six-digit code by concatenating and scrambling the actual time in seconds and the numerical value from a “secret” or “seed.” A TOTP has a short life span, typically thirty seconds. It changes at the :00 mark and :30 mark of each minute.

Why not just let the bank (or whatever) send me an OTP via text or email?

--> The answer is that neither texting nor email is (or was designed to be) a secure method for delivering anything, much less passwords of any kind.

## TOTP app on the market

- [Raivo OTP](https://github.com/raivo-otp/ios-application)
    - backs up to iCloud, makes your TOTPs available on all your iOS devices
- [Authy](https://authy.com/)
    - Cons:
        - requires a phone number for setup, not ideal for privacy concerns
        - Authy make it really difficult to break away from its ecosystem, to the point of sometimes not allowing individuals to delete their Authy accounts
    - Pros:
        - ease of cross-device syncing—on Authy’s servers—so you can access your TOTPs on your various devices and OSs
        - only provider that has full-fledged desktop apps as well as mobile apps
- [Google Authenticator](https://en.wikipedia.org/wiki/Google_Authenticator)
    - locked box, can not share TOTPs among multiple devices
    - not recommended
- [Microsoft Authenticator](https://www.microsoft.com/en-us/security/mobile-authenticator-app)
    - considered as a one-device-per-user app, not optimized for sharing TOTPs among multiple devices
    - best suited only for Microsoft-heavy workplaces
    - use only if you’re in a setting that requires Microsoft Authenticator, a proprietary kind of TOTP
