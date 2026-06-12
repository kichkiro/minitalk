<img src="https://github.com/kichkiro/kichkiro/blob/main/assets/banners/banner_minitalk.png?raw=true" width="100%"/>

# Minitalk

<i>
	<p>
		The purpose of this project is to code a small data exchange program using UNIX signals.
	</p>
</i>

#### <i>[subject](_subject/en.subject.pdf) v.2</i>

<details>
<summary><i><b>Project Structure  📂</b></i></summary>

```js
├── README.md
├── LICENSE
├── Dockerfile
├── project
│   ├── Makefile
│   ├── includes
│   │   ├── minitalk_bonus.h
│   │   └── minitalk.h
│   ├── lib
│   │   └── libft
│   └── src
│       ├── minitalk_client_bonus.c
│       ├── minitalk_client.c
│       ├── minitalk_server_bonus.c
│       └── minitalk_server.c
└── _subject
    └── en.subject.pdf
```
</details>

## 📌 - Key Topics

### UNIX Signals
Signal handling in Linux involves managing asynchronous notifications sent to processes by the kernel. Signals like SIGKILL, SIGTERM, and SIGSEGV trigger specific actions, which by default may terminate or ignore the process. Custom behavior can be defined using signal handlers, typically set via the signal() or sigaction() system calls, with the latter offering more control (e.g., using sigset_t for signal masks or SA_RESTART to handle interrupted system calls).

Critical functions include:

- kill(): To send signals.
- sigprocmask(): To block or unblock signals.

Proper signal handling is key to managing process termination, resource cleanup, and real-time event handling in concurrent environments, taking into account reentrancy and atomicity.

### Bitwise Operations
Bitwise operations are operations that directly manipulate individual bits of data. These are fundamental in low-level programming, especially when dealing with hardware interfaces, cryptographic algorithms, and performance-critical code. In C and many other languages, integers are typically represented in binary, and bitwise operators allow developers to perform logical operations directly on these binary representations.

Key bitwise operators in C include:

- AND (&): This operator compares each bit of two operands. The result is 1 if both corresponding bits are 1, otherwise 0.
- OR (|): Compares each bit of two operands. The result is 1 if at least one of the corresponding bits is 1.
- XOR (^): Compares each bit of two operands. The result is 1 if the corresponding bits differ, and 0 if they are the same.
- NOT (~): Inverts the bits of its operand, turning 1 into 0 and vice versa.
- Shift left (<<): Shifts the bits of the left operand to the left by the number of positions specified by the right operand, padding the vacated bits with 0. This is equivalent to multiplying the number by 2^n, where n is the number of positions shifted.
- Shift right (>>): Shifts the bits of the left operand to the right by the number of positions specified by the right operand. In unsigned integers, vacated bits are filled with 0, while in signed integers, the behavior can depend on the compiler.

## 🛠️ - Usage

``` sh
git clone --recurse-submodules https://github.com/kichkiro/minitalk.git
cd minitalk/
docker build -t minitalk:42 .
docker run -d --name minitalk minitalk:42
```
Now you can access to the container and start the server.

``` sh
docker exec -it minitalk bash
./server
```
Now open a new terminal and start the client with first argument the PID of the server and as second argument the message to be sent.

``` sh
docker exec -it minitalk bash
./client <PID> "<message>"
```
The message sent by the clinet will be visible in the server.

## ⚖️ - License

See [LICENSE](LICENSE)