# rust programming

## Box

Box allow to pass arround objects which size is not known at compile time.
e.g. when using traits

## Errors

To do generic errors just return 

```rust
Result<Smthing, Box<dyn Error>>
```

or you can use [anyhow](https://github.com/dtolnay/anyhow)

## traits

traits are a way to add genericity to rust that I did not use previously.

https://doc.rust-lang.org/rust-by-example/trait.html

You can pass arround objects implementing traits with `Box<dyn Obj>`

## Self

Self type, can be used in trait to reference implementing class type

## splitting crate in modules

https://doc.rust-lang.org/book/ch07-05-separating-modules-into-different-files.html

```rust
mod front_of_house;

pub use crate::front_of_house::hosting;

pub fn eat_at_restaurant() {
    hosting::add_to_waitlist();
    hosting::add_to_waitlist();
    hosting::add_to_waitlist();
}
```

```rust
pub mod hosting {
    pub fn add_to_waitlist() {}
}
```
