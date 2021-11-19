## Articles

Note: Excerpts are from sections that I think are especially useful or interesting.

- [Writing an OS in Rust](https://os.phil-opp.com/), Philipp Oppermann
- [Writing a Linux-compatible kernel in Rust](https://seiya.me/writing-linux-clone-in-rust), [Seiya Nuta][]

  > **Is Rust good for the kernel-land?**
  >
  > In my opinion, yes unless the target environment is not too resource-constrained.
  >
  > The kernel-land is a little bit eccentric: `panic!` will lead to a system crash, memory allocation failures should be handled without panicking, hidden control flows and hidden allocations are generally disliked.
  >
  > Rust's advantages also apply to the kernel-land. My favorite example is null-able pointer handling: if a pointer is nullable (i.e. `Option<NonNull<T>>`), you can't dereference it until you explicitly handle the null (`None`) case! Furthermore, using the new type idiom, you can distinguish between kernel and user pointers.
  >
  > However, we still have some issues with using Rust in the kernel-land:
  >
  > ...
- Rust has active page on the [osdev wiki](https://wiki.osdev.org/Rust)

[Seiya Nuta]: https://seiya.me/

## Major Projects

### tock

[`tockos.org`](https://www.tockos.org/)

> An embedded operating system designed for running multiple concurrent, mutually distrustful applications on low-memory and low-power microcontrollers.

### redox

[`redox-os.org`](https://www.redox-os.org/)

> Redox is a Unix-like Operating System written in Rust, aiming to bring the innovations of Rust to a modern microkernel and full set of applications.


### kerla

[`github.com/nuta/kerla`](https://github.com/nuta/kerla)

> Kerla is a monolithic operating system kernel from scratch in Rust which aims to be compatible with the Linux ABI, that is, runs Linux binaries without any modifications.

It's possible to SSH into a VM running Kerla right now:

```console
$ ssh root@kerla-demo.seiya.me
```

## Personal Projects

### liberty

[`github.com/LibertyOS-Development/kernel`](https://github.com/LibertyOS-Development/kernel)

> LibertyOS is something that will be unlike any existing operating system. LibertyOS is written primarily in Rust-an increasingly popular language for low-level programming (among other things). LOS is written entirely from scratch, down to its libraries, its programs, tests, and so on. LOS is also entirely free-to-use, and is open-sourced, so you are welcome to help make LOS even better!

