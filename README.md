# thread-amount

This is a fork of [`thread-amount`](https://github.com/jzeuzs/thread-amount), since
that crate is archived and no longer works.

[![Crate Version](https://img.shields.io/crates/v/thread-count)](https://crates.io/crates/thread-count)
[![Documentation](https://docs.rs/thread-count/badge.svg)](https://docs.rs/thread-count)
[![License](https://img.shields.io/crates/l/thread-count.svg)](./LICENSE)

**Get the amount of threads in the current process**

## Example Usage

`Cargo.toml`

```toml
[dependencies]
thread-amount = "0.1"
```

The code:

```rust
use thread_amount::thread_amount;

use std::thread;

fn main() {
    let amount = thread_amount();

    thread::spawn(move || {
        assert_eq!(amount.map(NonZeroUsize::get), Some(1))
    });
}
```

## Difference between [`num-threads`](https://crates.io/crates/num-threads)

This crate has windows support and reads the `/proc/[PID]/status` file in `-unix` systems.

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://tomio.fun/"><img src="https://avatars.githubusercontent.com/u/75403863?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Tomio</b></sub></a><br /><a href="https://github.com/devtomio/thread-amount/commits?author=devtomio" title="Code">💻</a> <a href="https://github.com/devtomio/thread-amount/commits?author=devtomio" title="Documentation">📖</a> <a href="#example-devtomio" title="Examples">💡</a> <a href="#infra-devtomio" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a> <a href="#maintenance-devtomio" title="Maintenance">🚧</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

## License

Licensed under the MIT license ([LICENSE](LICENSE) or <http://opensource.org/licenses/MIT>)
