# rs-local-chatbot

A simple asynchronous chat client implemented in Rust using the `tokio` runtime and `reqwest` for HTTP requests. This client allows users to interact with a chat model by sending messages and receiving responses.

## Features

- Asynchronous message handling
- Sends user messages to local ollama endpoint
- Receives and displays responses from the chat model
- Maintains conversation history

## Requirements

- Rust (1.58 or later)
- `tokio` crate
- `reqwest` crate
- `serde` and `serde_json` crates

## Installation

1. **Clone the repository:**

   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Add dependencies** to your `Cargo.toml`:

   ```toml
   [dependencies]
   tokio = { version = "1", features = ["full"] }
   reqwest = { version = "0.11", features = ["json"] }
   serde = { version = "1", features = ["derive"] }
   serde_json = "1"
   ```

3. **Build the project**:

   ```bash
   cargo build
   ```

## Usage

1. **Run the chat server** that the client will connect to. Ensure it is listening on `http://127.0.0.1:11434/api/chat`.

2. **Run the chat client**:

   ```bash
   cargo run
   ```

3. **Interact with the client**:

   - Type your message and press Enter.
   - The client will send the message to the chat API and display the assistant's response.

## Code Explanation

- **Structs**: 
  - `Response`: Represents the response from the chat API containing a message and a done flag.
  - `Message`: Represents a single message including the role (user or assistant) and the content.

- **Main Function**:
  - Initializes the message vector and the HTTP client.
  - Reads user input asynchronously and sends messages to the chat API.
  - Receives and processes responses, displaying them in real-time.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue for any suggestions or improvements.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.