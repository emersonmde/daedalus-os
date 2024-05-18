## DaedalusOS
DaedalusOS is a Rust based OS kernel following the [Writing an OS in Rust](https://os.phil-opp.com/) blog series by Philipp Oppermann.

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

## Current Progress
- ✅ [A Freestanding Rust Binary](https://os.phil-opp.com/freestanding-rust-binary/)
- ✅ [A Minimal Rust Kernel](https://os.phil-opp.com/minimal-rust-kernel/)
- [VGA Text Mode](https://os.phil-opp.com/vga-text-mode/)
- [Testing](https://os.phil-opp.com/testing/)
- [CPU Exceptions](https://os.phil-opp.com/cpu-exceptions/)
- [Double Faults](https://os.phil-opp.com/double-fault-exceptions/)
- [Hardware Interrupts](https://os.phil-opp.com/hardware-interrupts/)
- [Introduction to Paging](https://os.phil-opp.com/paging-introduction/)
- [Paging Implementation](https://os.phil-opp.com/paging-implementation/)
- [Heap Allocation](https://os.phil-opp.com/heap-allocation/)
- [Allocator Designs](https://os.phil-opp.com/allocator-designs/)
- [Async/Await](https://os.phil-opp.com/async-await/)