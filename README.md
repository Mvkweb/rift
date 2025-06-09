<p align="center">
  <a href="https://github.com/chawyehsu/rift">
    <img src="https://i.imgur.com/R10ivg9.png" alt="Banner with Rift Logo (Placeholder)">
  </a>
</p>

<p align="center">
 <a aria-label="Rift GitHub Repository" href="https://github.com/chawyehsu/rift"><img src="https://i.imgur.com/uvIy6cI.png" alt="Made by Chawye Hsu (Placeholder)"></a>
 <a aria-label="Join the Rift community on Discord (Placeholder)" href="#"><img alt="" src="https://i.imgur.com/qSfKisV.png" alt="Discord Badge (Placeholder)"></a>
</p>

<h1 align="center">Rift</h1>

> [!WARNING]
> Rift is under development and pre-release (version 0.1.0-beta.7). Some functionalities may appear broken, and there might be some bugs.

> [!NOTE]
> Please read our documentation at [https://github.com/chawyehsu/rift](https://github.com/chawyehsu/rift) before installing.

> [!IMPORTANT]
> For Rift-specific issues, please use [Rift GitHub Issues](https://github.com/chawyehsu/rift/issues) or the Rift Discord (if available) instead of Scoop support channels.

Rift is a CLI implementation of Scoop in Rust. It is a full-featured, practical, and efficient Rust reimplementation of [Scoop], the Windows command-line installer.

## Changes from vanilla Scoop

- **Rust Implementation**: Built in Rust for performance, safety, and reliability, leveraging Rust's strong type system and memory safety guarantees.
- **Efficient**: Designed for practical and efficient interaction with the Scoop ecosystem, aiming for faster execution and lower resource consumption.
- **Full-featured**: Aims to provide all core functionalities of Scoop, offering a familiar experience to existing Scoop users.
- **Modern CLI**: Utilizes modern Rust CLI practices and libraries for a robust and user-friendly command-line experience.

## Installation

Please refer to the [official GitHub repository](https://github.com/chawyehsu/rift) for detailed installation instructions, including how to install from source or pre-built binaries.

## Local Development

To set up a local development environment:

1.  Clone the repository:
    ```bash
    git clone https://github.com/chawyehsu/rift.git
    cd rift
    ```
2.  Run the application:
    ```bash
    cargo run -- help
    ```

## Star History

<a href="https://star-history.com/#chawyehsu/rift&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=chawyehsu/rift&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=chawyehsu/rift&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=chawyehsu/rift&type=Date" />
  </picture>
</a>

## License

Rift is licensed under the Apache-2.0 License.

[Scoop]: https://scoop.sh/
