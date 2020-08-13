<img align="right" width="25%" src="logo.png">

This is an active GitHub mirror of the WebGPU implementation in Rust, which now lives in "gfx/wgpu" of [Mozilla-central](https://hg.mozilla.org/mozilla-central/file/tip/gfx/wgpu). Issues and pull requests are accepted, but some bidirectional synchronization may be involved.

# WebGPU

[![Matrix](https://img.shields.io/badge/Dev_Matrix-%23wgpu%3Amatrix.org-blueviolet.svg)](https://matrix.to/#/#wgpu:matrix.org) [![Matrix](https://img.shields.io/badge/User_Matrix-%23wgpu--users%3Amatrix.org-blueviolet.svg)](https://matrix.to/#/#wgpu-users:matrix.org)
[![Build Status](https://github.com/gfx-rs/wgpu/workflows/CI/badge.svg)](https://github.com/gfx-rs/wgpu/actions)

This is the core logic of an experimental [WebGPU](https://www.w3.org/community/gpu/) implementation. It's written in Rust and is based on [gfx-hal](https://github.com/gfx-rs/gfx) with help of [gfx-extras](https://github.com/gfx-rs/gfx-extras). See the upstream [WebGPU specification](https://gpuweb.github.io/gpuweb/) (work in progress).

The implementation consists of the following parts:

  - [![Crates.io](https://img.shields.io/crates/v/wgpu-core.svg?label=wgpu-core)](https://crates.io/crates/wgpu-core) [![docs.rs](https://docs.rs/wgpu-core/badge.svg)](https://docs.rs/wgpu-core/) - internal Rust API for WebGPU implementations to use
  - [![Crates.io](https://img.shields.io/crates/v/wgpu-types.svg?label=wgpu-types)](https://crates.io/crates/wgpu-types) [![docs.rs](https://docs.rs/wgpu-types/badge.svg)](https://docs.rs/wgpu-types/) - Rust types shared between `wgpu-core`, `wgpu-native`, and `wgpu-rs`
  - [![Crates.io](https://img.shields.io/crates/v/wgpu-subscriber.svg?label=wgpu-subsciber)](https://crates.io/crates/wgpu-subscriber) [![docs.rs](https://docs.rs/wgpu-subscriber/badge.svg)](https://docs.rs/wgpu-subscriber/) - tracing subscribers to use with `wgpu`
  - `player` - standalone application for replaying the API traces, uses `winit`

This repository contains the core of `wgpu`, and is not usable directly by applications.
If you are looking for the user-facing Rust API, you need [wgpu-rs](https://github.com/gfx-rs/wgpu-rs).
If you are looking for the native implementation or bindings to the API in other languages, you need [wgpu-native](https://github.com/gfx-rs/wgpu-native).

## Supported Platforms

   API   |    Windows 7/10    |  Linux & Android   |    macOS & iOS     |
  -----  | ------------------ | ------------------ | ------------------ |
  DX11   | :white_check_mark: |                    |                    |
  DX12   | :heavy_check_mark: |                    |                    |
  Vulkan | :heavy_check_mark: | :heavy_check_mark: |                    |
  Metal  |                    |                    | :heavy_check_mark: |
  OpenGL | :construction:     | :construction:     | :construction:     |

:heavy_check_mark: = Primary support — :white_check_mark: = Secondary support — :construction: = Unsupported, but support in progress
