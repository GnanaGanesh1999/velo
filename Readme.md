# Velo 🚵 
![Rust](https://img.shields.io/badge/Rust-lang-000000.svg?style=flat&logo=rust)[![codecov](https://codecov.io/gh/StaffEngineer/velo/branch/main/graph/badge.svg?token=QGEKLM6ZDF)](https://codecov.io/gh/StaffEngineer/velo)

![alt text](velo.png "Velo")

## Demo

This app is primarily designed for native desktop platforms, and its
WebAssembly (wasm) target has a limited feature set. wasm target is best
suited for quick document sharing and editing, currently only landscape
mode is supported (tested on Chrome):

[<https://staffengineer.github.io/velo?document=https://gist.githubusercontent.com/StaffEngineer/3dc607976ea4ed695662a8fe9e3281a3/raw/8c8994c7b3051b7b8db58e20de2b6ab2d791b89d/velo.json>](https://staffengineer.github.io/velo?document=https://gist.githubusercontent.com/StaffEngineer/3dc607976ea4ed695662a8fe9e3281a3/raw/8c8994c7b3051b7b8db58e20de2b6ab2d791b89d/velo.json)

## Inspiration

At work, I frequently rely on lucid.app to brainstorm ideas with my
colleagues or by myself. Typically, I share my ideas by sending either
the diagrams themselves or screenshots of them. While I tend to stick
with simple features like rectangles and arrows, I\'ve been
contemplating the idea of creating a similar tool in Rust. Not only
would it allow me to learn the language, but it would also be an
enjoyable project to work on.

## What\'s implemented:
-   support rectangle/circle nodes
-   add/remove node
-   node resizing
-   node repositioning
-   wrapped text inside nodes
-   paste screenshot from clipboard [native target only]
-   connect nodes with arrows
-   make app snapshot in memory and load from it (MacOs: Command + s\[l\])
-   save app state to db and load from it
-   change background color of nodes
-   move node to front/back
-   positioning text inside node
-   buttons to cut/copy/paste text
-   multiple documents/tabs support
-   load app state from url
-   ability to create sharable url of the document using \"Share
    Document\" button (**.velo.toml** should be created in user home
    directory containing GitHub access token with \"gist\" scope) [native target only]:

   ```toml
   github_access_token = "<github_access_token>"
   ```

- initial markdown support
  - italic/bold text style
  - links
  - syntax highlighting

## Run

Native:

```sh
cargo r 
```

Wasm:

```sh
cargo r --target wasm32-unknown-unknown
```

To create app bundle with icon (tested only on MacOS):

```sh
cargo install cargo-bundle
cargo bundle
```

## Pre-commit actions

```sh
cargo fmt
cargo clippy --fix --allow-staged -- -A clippy::type_complexity -A clippy::too_many_arguments
```

# Contributing

Contributions are always welcome! Please adhere to this project\'s code
of conduct. If you have questions or suggestions, feel free to make an
[issue](https://github.com/StaffEngineer/velo/issues).

❤️