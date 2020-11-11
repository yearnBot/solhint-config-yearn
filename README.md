---
config: Solhint and Solhint-Prettier-Plugin
version: "0.1.0"
title: "Yearn Finance | Solhint Shareable Configuration"
---

# Yearn Solhint Configuration

![Recommended Badge](https://img.shields.io/badge/-Recommended-brightgreen)
![Category Badge](https://img.shields.io/badge/-Security%20Rules-informational)
![Default Severity Badge warn](https://img.shields.io/badge/Default%20Severity-warn-yellow)

> The `{"extends": "yearn"}` property in a configuration file enables these
> rule.

# Overview

Shareable configs are configurations that you can use and extend from. They can
be useful for using the same base configuration in all your projects or for
basing your configuration from a well-known one.

To use a shareable config, you have to add it to your Solhint configuration:

```javascript
  "extends": ["solhint-config-yearn"]
```

## Creating your own shareable config

Shareable configs are regular npm packages. There are only two conditions:

- The name of the package must start with `solhint-config-`
- The package must export a regular object with the same structure as a regular
  configuration object (i.e. the one in your `.solhint.json`).

## Examples

Avoid to use low level calls.

### Options

This rule accepts a string option of rule severity. Must be one of "error",
"warn", "off". Default to warn.

#### Example Config

```json
{
  "rules": {
    "avoid-low-level-calls": "warn"
  }
}
```

### Examples

#### 👎 Examples of **incorrect** code for this rule

##### Using low level calls

```solidity
msg.sender.call(code);
a.callcode(test1);
a.delegatecall(test1);
```

## Version

Yearn Config uses at least version
[Solhint 1.1.6](https://github.com/protofire/solhint/tree/v1.1.6)

## Resources

- [Rule source](https://github.com/protofire/solhint/tree/master/lib/rules/security/avoid-low-level-calls.js)
- [Document source](https://github.com/protofire/solhint/tree/master/docs/rules/security/avoid-low-level-calls.md)
- [Test cases](https://github.com/protofire/solhint/tree/master/test/rules/security/avoid-low-level-calls.js)

## License

Copyright 2020 Yearn Contributors

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
