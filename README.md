# Project Analysis: Rift

Rift is a command-line interface (CLI) tool written in Rust that serves as a reimplementation of Scoop, a Windows command-line installer.

## How it works:

1.  **Entry Point**: The execution begins in [`src/bin/rift.rs`](src/bin/rift.rs:1), which calls the `rift::create_app()` function.
2.  **Application Initialization**: The [`create_app()`](src/lib.rs:34) function in [`src/lib.rs`](src/lib.rs:34) handles initial setup, including logging, and then delegates control to `cmd::start()`.
3.  **Command Line Interface (CLI) Handling**: The [`cmd::start()`](src/cmd/mod.rs:78) function, defined in [`src/cmd/mod.rs`](src/cmd/mod.rs:78), is responsible for parsing command-line arguments using the `clap` crate. It defines and dispatches various subcommands such as `bucket`, `cache`, `install`, `update`, `uninstall`, and more, which mirror Scoop's functionalities.
4.  **Core Logic (libscoop)**: Before executing a specific command, `cmd::start()` initializes a [`libscoop::Session`](crates/libscoop/src/lib.rs:23). This `Session` object acts as a central handle to the global state of `libscoop` and is passed to the respective command execution functions (e.g., `bucket::execute`, `install::execute`). The `libscoop` crate, located in [`crates/libscoop`](crates/libscoop/src/lib.rs), provides the underlying logic for interacting with Scoop, managing buckets, handling package operations, caching, and configuration.
5.  **Hashing (scoop_hash)**: The `scoop_hash` crate, found in [`crates/scoop_hash`](crates/scoop_hash/src/lib.rs), offers various hashing algorithms (MD5, SHA1, SHA256, SHA512). These are likely utilized by `libscoop` to verify the integrity of downloaded packages through checksum validation during installation or update processes.

## Overall Flow:

When a user executes a `rift` command, the application parses the command and its arguments. It then initializes a `libscoop` session and dispatches the command to the appropriate handler within the `cmd` module. These handlers leverage the functionalities provided by the `libscoop` crate to perform the requested Scoop-like operation, often using the `scoop_hash` crate for checksum verification.

## Project Architecture Diagram:

```mermaid
graph TD
    A[User executes rift command] --> B{src/bin/rift.rs};
B --> C[src/lib.rs.create_app()];
C --> D[src/cmd/mod.rs.start()];
    D -- Parses CLI arguments --> E[clap crate];
    D -- Initializes --> F[libscoop::Session];
    D -- Dispatches command to --> G{Command Handlers (e.g., cmd/install.rs)};
    G -- Utilize --> F;
    F -- Uses for checksums --> H[scoop_hash crate];
    F -- Interacts with Scoop ecosystem --> I[Scoop Buckets/Packages];
```

## Proposed Plan:

1.  **Confirm Understanding**: I have provided a detailed analysis of the project's purpose and architecture. Please review this understanding and let me know if it aligns with your expectations or if there are any areas you'd like me to clarify or explore further.
2.  **Further Exploration (Optional)**: If you'd like a deeper dive into specific functionalities (e.g., how `install` works internally, or the details of `libscoop`'s package management), please specify which areas you'd like me to investigate.
3.  **Document Plan**: Once you confirm the understanding and plan, I can write this analysis to a markdown file for your reference.
4.  **Switch Mode**: After the plan is finalized, I will switch to "code" mode to proceed with any implementation tasks you might have based on this analysis.
