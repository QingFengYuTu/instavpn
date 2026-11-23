# instavpn

Setting up an L2TP/IPsec VPN server also means managing user passwords and a shared IPsec key. instavpn is a Python VPN server management tool with commands for those tasks and a web interface for administration.

## Features

- Create VPN users, retrieve their passwords, and delete accounts from the CLI.
- Read or replace the IPsec pre-shared key.
- Show stored credentials and bandwidth statistics.
- Enable or disable the web interface and set its login credentials.

## Installation

The original project lists Ubuntu 14.04 and 512 MB RAM as its requirements. **Ubuntu 14.04 is obsolete; support for current distributions is not established by the available documentation.** Test in an isolated environment before deployment.

From a source checkout that contains `instavpn.sh`, inspect the installer and run it:

```sh
less instavpn.sh
sudo bash instavpn.sh
```

This Python project uses a shell installer in its documented installation flow. No `pip` installation procedure or Python version requirement is documented.

## Usage

Create a VPN account and inspect the configured users:

```sh
instavpn user set alice change-this-password
instavpn user list
```

Replace the example password before use. To retrieve an account password or delete an account:

```sh
instavpn user get alice
instavpn user delete alice
```

Read or change the IPsec pre-shared key:

```sh
instavpn psk get
instavpn psk set change-this-shared-key
```

Show all credentials or bandwidth statistics:

```sh
instavpn list
instavpn stat
```

**Credential commands can print secrets, and passwords passed as arguments may remain in shell history.** Avoid sharing their output or running them in recorded terminal sessions.

Set web interface credentials and enable the interface:

```sh
instavpn web set admin change-this-admin-password
instavpn web mode on
```

Browse to `http://IP-ADDRESS:8080`, with `IP-ADDRESS` replaced by the server address. The documented URL uses HTTP; restrict access to a trusted network rather than exposing it publicly.

Disable the interface when it is no longer needed:

```sh
instavpn web mode off
```

## License

Licensed under Apache-2.0. This project is based on [sockeye44/instavpn](https://github.com/sockeye44/instavpn). Retain applicable upstream copyright, license, and attribution notices when redistributing the code.

## Related projects

These repositories were supplied as other projects from the same author. Their purposes were not included in the available information:

- [ProjectKangcutz/modelfusion](https://github.com/ProjectKangcutz/modelfusion): No verified functionality description was provided.
- [boostlyapi/seagull](https://github.com/boostlyapi/seagull): No verified functionality description was provided.
- [mwitimugao/cabin](https://github.com/mwitimugao/cabin): No verified functionality description was provided.

