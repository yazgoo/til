# macroquad

## running app without macro

```rust
macroquad::Window::new("MyApp", my_main_async_method());
```

## loading texture from bytes

```rust
let quad_context = unsafe { get_internal_gl() }.quad_context;
Texture2D::from_file_with_format(quad_context, &bytes[..], None)
```
