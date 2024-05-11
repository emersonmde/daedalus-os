## DaedalusOS

## Running

Building requires Rust nightly and Rust source
```bash
rustup toolchain install nightly --allow-downgrade
rustup component add rust-src.
```

Building also requires the `bootimage` tool to link the kernel with the bootloader
```bash
cargo install bootimage
```

To run the bootimage, `llvm-tools-preview` must be installed
```bash
rustup component add llvm-tools-preview
```

Then use the `bootimage` tool to create the bootable disk image
```bash
cargo bootimage
```

To run the kernel in QEMU, run the following command
```bash
qemu-system-x86_64 -drive format=raw,file=target/x86_64-daedalus-os/debug/bootimage-daedalus-os.bin
```