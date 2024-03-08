---
title: 2024-03-04-anthropic-api-dependency-error
tags:
  - blog
---
1:00pm -08:00 (1709586005843)
Error when using Anthropic?
```zh
from typing_extensions import deprecated
ImportError: cannot import name 'deprecated' from 'typing_extensions' (/Users/michael/Library/Python/3.9/lib/python/site-packages/typing_extensions.py)
```
Easy fix:
```zsh
pip install anthropic

Installing collected packages: typing-extensions
  Attempting uninstall: typing-extensions
    Found existing installation: typing_extensions 4.4.0
    Uninstalling typing_extensions-4.4.0:
      Successfully uninstalled typing_extensions-4.4.0
ERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
mitmproxy 9.0.1 requires typing-extensions<4.5,>=4.3; python_version < "3.10", but you have typing-extensions 4.10.0 which is incompatible.
tensorflow 2.13.0 requires typing-extensions<4.6.0,>=3.6.6, but you have typing-extensions 4.10.0 which is incompatible.
```

The reason for my error: in between the last time I ran a script with `anthropic`, I've installed `mitmproxy`.  And `mitmproxy` uses a different version than Anthropic does.
Easiest fix ever!