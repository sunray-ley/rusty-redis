# RustyRedis

RustyRedis is a Redis written in Rust, including a Redis client and a Redis server.

## Features

- Supports common Redis data structures such as strings, hash tables, lists, etc

- Provides a complete set of Redis commands, including GET, SET, HGET, HSET, LPUSH, LPOP, etc

- Implements client-server communication over TCP using an efficient networking library

- Codebase is clean, readable, and maintainable

## Installation

Make sure you have Rust programming language and Cargo package manager installed. Execute the following commands in the terminal to install:

```shell
cargo install rusty-redis
```

## Usage

### Running the Redis Server

To run RustyRedis as a Redis server, execute the following command:

```shell
rusty-redis-server
```

The server will listen for client connections on the default port 6379. You can also specify a different port number using command-line arguments.

### Running the Redis Client

To connect to the Redis server using the RustyRedis client, execute the following command:

```shell
rusty-redis-client
```

The client will prompt you to enter commands and display the command execution results.

### API Example

RustyRedis provides a simple and easy-to-use API that you can directly use in your Rust projects. Here's a simple example:

```rust
use rusty_redis::client::RedisClient;

fn main() {
    let mut client = RedisClient::new("127.0.0.1", 6379).unwrap();

    // Set key-value pair
    client.set("name", "John").unwrap();

    // Get value by key
    let name: Option<String> = client.get("name").unwrap();
    println!("Name: {:?}", name);

    // Execute Redis command
    let response: String = client.command("PING").unwrap();
    println!("Response: {}", response);
}
```

For more information on API usage, please refer to the API documentation.

## Contributing

Contributions to RustyRedis are welcome! If you have any suggestions or questions, please open an issue or pull request on GitHub.

## License

RustyRedis is distributed under the MIT License. Please refer to the [LICENSE](https://github.com/sunray-ley/rusty-redis/blob/main/LICENSE) file for more information.
