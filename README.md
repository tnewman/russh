# Russh
[![Rust](https://github.com/warp-tech/russh/actions/workflows/rust.yml/badge.svg)](https://github.com/warp-tech/russh/actions/workflows/rust.yml)  <!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-7-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

Low-level Tokio SSH2 client and server implementation.

This is a fork of [Thrussh](https://nest.pijul.com/pijul/thrussh) by Pierre-Étienne Meunier:

> ✨ = added in Russh

* More safety guarantees ✨
* `forward-tcpip` (remote port forwarding) ✨
* Ciphers:
  * `chacha20-poly1305@openssh.com`
  * `aes256-gcm@openssh.com` ✨
  * `aes256-ctr` ✨
  * `aes192-ctr` ✨
  * `aes128-ctr` ✨
* Key exchanges:
  * `curve25519-sha256@libssh.org`
  * `diffie-hellman-group1-sha1` ✨
  * `diffie-hellman-group14-sha1` ✨
  * `diffie-hellman-group14-sha256` ✨
* MACs:
  * `hmac-sha1` ✨
  * `hmac-sha2-256` ✨
  * `hmac-sha2-512` ✨
  * `hmac-sha1-etm@openssh.com` ✨
  * `hmac-sha2-256-etm@openssh.com` ✨
  * `hmac-sha2-512-etm@openssh.com` ✨
* Host keys:
  * `ssh-ed25519`
  * `rsa-sha2-256`
  * `rsa-sha2-512`
  * `ssh-rsa` ✨
* Dependency updates
* OpenSSH keepalive request handling ✨
* OpenSSH agent forwarding channels ✨

## Safety

* `deny(clippy::unwrap_used)`
* `deny(clippy::expect_used)`
* `deny(clippy::indexing_slicing)`
* `deny(clippy::panic)`
* Exceptions are checked manually

### Panics

* When the Rust allocator fails to allocate memory during a CryptoVec being resized.

### Unsafe code

* `cryptovec` uses `unsafe` for faster copying, initialization and binding to native API.

## Ecosystem

* [russh-sftp](https://crates.io/crates/russh-sftp) - server-side SFTP subsystem support for `russh` - see `russh/examples/sftp_server.rs`.
* [async-ssh2-tokio](https://crates.io/crates/async-ssh2-tokio) - simple high-level API for running commands over SSH.

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center"><a href="https://github.com/mihirsamdarshi"><img src="https://avatars.githubusercontent.com/u/5462077?v=4?s=100" width="100px;" alt="Mihir Samdarshi"/><br /><sub><b>Mihir Samdarshi</b></sub></a><br /><a href="https://github.com/warp-tech/russh/commits?author=mihirsamdarshi" title="Documentation">📖</a></td>
      <td align="center"><a href="https://peet.io/"><img src="https://avatars.githubusercontent.com/u/2230985?v=4?s=100" width="100px;" alt="Connor Peet"/><br /><sub><b>Connor Peet</b></sub></a><br /><a href="https://github.com/warp-tech/russh/commits?author=connor4312" title="Code">💻</a></td>
      <td align="center"><a href="https://github.com/kvzn"><img src="https://avatars.githubusercontent.com/u/313271?v=4?s=100" width="100px;" alt="KVZN"/><br /><sub><b>KVZN</b></sub></a><br /><a href="https://github.com/warp-tech/russh/commits?author=kvzn" title="Code">💻</a></td>
      <td align="center"><a href="https://www.telekom.de"><img src="https://avatars.githubusercontent.com/u/21334898?v=4?s=100" width="100px;" alt="Adrian Müller (DTT)"/><br /><sub><b>Adrian Müller (DTT)</b></sub></a><br /><a href="https://github.com/warp-tech/russh/commits?author=amtelekom" title="Code">💻</a></td>
      <td align="center"><a href="https://www.evilsocket.net"><img src="https://avatars.githubusercontent.com/u/86922?v=4?s=100" width="100px;" alt="Simone Margaritelli"/><br /><sub><b>Simone Margaritelli</b></sub></a><br /><a href="https://github.com/warp-tech/russh/commits?author=evilsocket" title="Code">💻</a></td>
      <td align="center"><a href="http://joegrund.com"><img src="https://avatars.githubusercontent.com/u/458717?v=4?s=100" width="100px;" alt="Joe Grund"/><br /><sub><b>Joe Grund</b></sub></a><br /><a href="https://github.com/warp-tech/russh/commits?author=jgrund" title="Code">💻</a></td>
      <td align="center"><a href="https://github.com/AspectUnk"><img src="https://avatars.githubusercontent.com/u/59799956?v=4?s=100" width="100px;" alt="AspectUnk"/><br /><sub><b>AspectUnk</b></sub></a><br /><a href="https://github.com/warp-tech/russh/commits?author=AspectUnk" title="Code">💻</a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
