# how-to-rust
A collection of blog posts and links that talk about how to successfully use Rust.

This repo is meant to be a list of links pointing at great blog posts about using Rust. I am particularly interested in collecting posts that discuss how to overcome borrow checker errors that arise or how to best make use of the borrow checker to enforce interesting properties.

I have some vague ideas of turning this repo from a collection of links into a nice mdbook, but for now, I'm just accumulating data! Pull requests adding interesting articles (or adjusting the categorizations) are very welcome!

## Structuring code

### [Caches in Rust](https://matklad.github.io//2022/06/11/caches-in-rust.html) by [Aleksey Kladov](https://github.com/matklad/)

Discusses techniques for making a "lazilly allocated" cache, where the entry is populated when it is used. Suggests patterns where the methods are `fn get(&self) -> &Value` (rather than, e.g., `fn get(&mut self) -> &Value`).

### [Using Rust for Game Development](https://www.youtube.com/watch?v=aKLntZcp27M) by [Katherine West](https://github.com/kyren) (video)

Discusses ECS but also the idea of storing your data in a vec (or other container) and passing around indices (or other keys) to act as pointers. Also covers generational arenas (like [generational-arena](https://crates.io/crates/generational-arena)) which can help manage alloc/free patterns in these sorts of structures.

### [Modeling graphs in Rust using vector indices](http://smallcultfollowing.com/babysteps/blog/2015/04/06/modeling-graphs-in-rust-using-vector-indices/) by [Niko Matsakis](https://github.com/nikomatsakis/)

Discusses the idea of storing your data in a vec (or other container) and passing around indices (or other keys) to act as pointers. Note that generational arenas (covered by West in previous item) can help solve the problem of "how to remove a node without dangling indices", although they only detect dangling indices at runtime, they don't prevent them statically.
