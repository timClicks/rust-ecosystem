## Articles

Note: Excerpts are from sections that I think are especially useful or interesting.

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

[Seiya Nuta]: https://seiya.me/

## Projects

### kerla

[`github.com/nuta/kerla`](https://github.com/nuta/kerla)

> Kerla is a monolithic operating system kernel from scratch in Rust which aims to be compatible with the Linux ABI, that is, runs Linux binaries without any modifications.

It's possible to SSH into a VM running Kerla right now:

```console
$ ssh root@kerla-demo.seiya.me
```
