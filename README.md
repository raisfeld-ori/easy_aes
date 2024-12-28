# very simple AES

aes is complicated, and I realized I still have some old cbc functions for encrypting and decrypting.
So I thought I would turn it into a package so you can also use it!

## usage

every single encryption and decryption requires a name, password, and the data you want to encrypt. the output is
the encrypted bytes of the data.

Example:

```rust
fn main(){
    let name = "joe";
    let password = "1234";
    let data = b"my very important secret";

    let encrypted = aes_encrypt(name, password, data);
    println!("Encrypted: {:?}", encrypted.to_vec()); // [229, 138, 19 ... 113, 59]
    let decrypted = aes_decrypt(name, password, &encrypted);
    println!("Decrypted: {}", String::from_utf8_lossy(decrypted.as_slice())); // my very important secret
}
```
