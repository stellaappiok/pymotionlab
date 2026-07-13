# Security Policy

## Supported versions

PyMotionLab is currently pre-1.0 and under active development. Security fixes will target the latest released version on PyPI once publishing begins.

| Version | Supported |
|---|---|
| main / unreleased | :white_check_mark: |
| < 0.1 | :x: |

## Reporting a vulnerability

If you discover a security vulnerability in PyMotionLab (for example, unsafe deserialization of config files, arbitrary code execution via loaded arm specs, or a dependency with a known CVE):

1. **Do not open a public GitHub issue.**
2. Report it privately via GitHub's "Report a vulnerability" feature (Security tab on the repository), or by emailing the maintainer directly (see repository profile for contact info).
3. Include: a description of the vulnerability, steps to reproduce, and the potential impact.

You should expect an initial response within 5 business days. Since this is a small, actively-developed project maintained largely by one person, timelines may vary — but reports will not be ignored.

## Disclosure process

Once a reported vulnerability is confirmed:

1. A fix is developed and tested privately.
2. A new version is released with the fix.
3. The vulnerability is disclosed publicly (with credit to the reporter, unless they prefer to remain anonymous) after the fix is available.

## Scope

This policy covers the PyMotionLab Python package itself. It does not cover vulnerabilities in third-party dependencies (report those upstream) or in example/demo code outside the core library.
