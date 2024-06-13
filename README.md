Tutorial Nexus ZKVM

Need VPS Recommend Spec:

2 Core
4 GB Ram
install package

   ```sudo apt update -y && sudo apt upgrade -y && sudo apt install cmake -y && sudo apt install build-essential -y && curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh   ```

wait until complete and enter

setup cargo

   ``` . "$HOME/.cargo/env" && rustup target add riscv32i-unknown-none-elf && cargo install --git https://github.com/nexus-xyz/nexus-zkvm nexus-tools --tag 'v1.0.0' && cargo nexus new nexus-project && cd nexus-project && cd src && rm -rf main.rs && cat <> main.rs #![no_std] #![no_main]    ```
fn fib(n: u32) -> u32 { match n { 0 => 0, 1 => 1, _ => fib(n - 1) + fib(n - 2), } }

#[nexus_rt::main] fn main() { let n = 7; let result = fib(n); assert_eq!(result, 13); } EOT
   ```

run program

   ```cargo nexus run
   ```
generate proof

   ```cargo nexus prove   ```

verify your proof

   ```cargo nexus verify   ```

save your proof locally (on your phone/pc), follow the video above

