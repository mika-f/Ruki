# Roki

This crate provides parser function for Windows Portable Executable (PE32, PE32+, PE32 .NET) Format File.

## Usage

Add this to your `Cargo.toml`

```toml
[dependencies]
roki = "0.1"
```

## Example

```rust
use roki::Executable;

fn main() -> Result<(), exitfailure::ExitFailure> {
  let path = Path::new("./path/to/windows/executable.dll");
  let mut executable = Executable::new(&path)?;
  executable.parse()?;

  // You can find examples of this crate in ../roco directory.
  println!("{}", executable.dos_header().unwrap().is_windows_executable()); // => true
}
```
