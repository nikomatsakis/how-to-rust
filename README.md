# how-to-rust
A collection of blog posts and links that talk about how to successfully use Rust.

This repo is meant to be a list of links pointing at great blog posts about using Rust. I am particularly interested in collecting posts that discuss how to overcome borrow checker errors that arise or how to best make use of the borrow checker to enforce interesting properties.

I have some vague ideas of turning this repo from a collection of links into a nice mdbook, but for now, I'm just accumulating data! Pull requests adding interesting articles (or adjusting the categorizations) are very welcome!

## Structuring code

### [Caches in Rust](https://matklad.github.io//2022/06/11/caches-in-rust.html) by [Aleksey Kladov](https://github.com/matklad/)

Discusses techniques for making a "lazilly allocated" cache, where the entry is populated when it is used. Suggests patterns where the methods are `fn get(&self) -> &Value` (rather than, e.g., `fn get(&mut self) -> &Value`).
