---
title: disclosure-policy
tags:
  - blog
date: 2024-02-04
---
# Responsible Disclosure Policy for smolkin.org

We take the security of our systems seriously, and we value the security community. The responsible disclosure of security vulnerabilities helps us ensure the security and privacy of our users.

## Guidelines

We require that all researchers:

- Make every effort to avoid privacy violations, degradation of user experience, disruption to production systems, and destruction of data during security testing;
- Perform research only within the scope set out below;
- Use the identified communication channels to report vulnerability information to us; and
- Keep information about any vulnerabilities you've discovered confidential between yourself and Sam Bowne until we've had 15 days to resolve the issue.

If you follow these guidelines when reporting an issue to us, we commit to:

- Not pursue or support any legal action related to your research;
- Work with you to understand and resolve the issue quickly (including an initial confirmation of your report within 72 hours of submission);
- Recognize your contribution on our [Security Researcher Hall of Fame](https://smolkin.org/hall-of-fame.htm), if you are the first to report the issue and we make a code or configuration change based on the issue.

## Scope

Materials hosted on these servers:

- www.smolkin.org
- michael.smolkin.org
- notes.smolkin.org

## Out of scope

Any services hosted by 3rd party providers and services are excluded from scope. These services include, but are not limited to:

- Any part of the UCDAVIS.EDU or CCSF.EDU or MIT.EDU domains
- Any part of the ~~TWITTER.COM~~ X.COM or FACEBOOK.COM domains
- Any part of the GOOGLE.COM or GMAIL.COM or YOUTUBE.COM domains
- And parts of any other domains not hosted by smolkin.org

In the interest of the safety of our users, staff, the Internet at large and you as a security researcher, the following test types are excluded from scope:

- Findings from physical testing such as office access (e.g. open doors, tailgating)
- Findings derived primarily from social engineering (e.g. phishing, vishing)
- Findings from applications or systems not listed in the 'Scope' section
- Network level Denial of Service (DoS/DDoS) vulnerabilities

## Intentional Vulnerabilities

The attack server contains several hacking games, which intentionally have vulnerabilities such as SQLi and XSS. The only vulnerabilities worth reporting on them would be a way to break or cheat on the games.

## Things we do not want to receive

Personally identifiable information (PII)

## How to report a security vulnerability?

If you believe you've found a security vulnerability please send it to us by emailing security [at] smolkin.org or hit the contact us button. Please include the following details with your report:

- Description of the location and potential impact of the vulnerability;
- A detailed description of the steps required to reproduce the vulnerability (POC scripts, screenshots, and compressed screen captures are all helpful to us); and
- Your name/handle and a link for recognition in our Hall of Fame.

If you'd like to encrypt the information, please email security [at] smolkin.org to get a GPG key.

## Source

Based on this document:

[Responsible Disclosure Policy (Example)](https://github.com/bugcrowd/disclosure-policy/blob/master/responsible_disclosure_policy.md)

---

H/T [Sam Bowne](https://samsclass.info/vuln-disclosure-policy.htm)
