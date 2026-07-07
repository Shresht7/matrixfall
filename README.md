# `matrixfall`

The matrixfall effect in the terminal.

![demo](./demo.gif)

> [!NOTE]
>
> Just a simple program I made while learning Rust!

## 🌟 Features

- Multiple character symbol sets, including original `Katakana` symbols, `binary`, `decimal`, `mathematical` symbols, `ASCII` characters, `Braille` patterns and more.
- Customizable stream colors and gradients.
- Adjustable frame rate, stream count, and spacing.
- Option to leave a trail of characters as the streams pass by.
- Randomized symbol switching for added visual interest.

---

## 🛠️ Installation

> [!NOTE]
> 
> To install and run matrixfall, you will need to have Rust and Cargo installed on your system. You can install Rust and Cargo by following the instructions at [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install).

You can clone the repository and build the project:

```sh
git clone https://github.com/Shresht7/matrixfall.git
cd matrixfall
cargo build --release
```

To run the project, use the following command:

```sh
cargo run --release
```

Or **alternatively**, you can also install `matrixfall` using `cargo install` and add it to your `$PATH` variable for easy access:

```sh
cargo install --path . --name matrixfall
```

After installation, you can run matrixfall from anywhere by adding the Cargo bin directory to your `$PATH` variable.

---

## 📖 Usage Instructions

To use matrixfall, you can run the project with the following command:

```sh
matrixfall [OPTIONS]
```

Here are some examples of how to use the different configuration options:

- To use the original Katakana symbols with the default settings:
  ```sh
  matrixfall
  ```

- To use binary symbols with a custom stream color and gradient:
  ```sh
  matrixfall --mode binary --stream-color 0,255,70 --stream-color-gradient-factor 0.5
  ```

- To use ASCII characters with a higher frame rate and leave a trail:
  ```sh
  matrixfall --mode ASCII --fps 120 --leave-trail
  ```

> [!TIP]
> 
> You can combine multiple options to customize the matrixfall effect to your liking.

### Configuration Options

The different configuration options available in this project are:

* `mode`: The character symbol set to use. Valid options include "Original", "Binary", "Decimal", "Math", "ASCII", "Braille", "Emoji", and custom sets like "abc123".
* `stream_color`: The color of the streaming entities (e.g., `"0,255,70"`, `"#00FF00"`, or `"green"`).
* `stream_color_gradient_factor`: The multiplier that describes the extent of the gradient in the stream color.
* `leading_entity_color`: The color of the leading entity in a stream (e.g., `"200,255,200"`, `"#C8FFC8"`, or `"white"`).
* `leave_trail`: A boolean option to leave the trail intact as the streams pass by.
* `fps`: The frame rate to run at, specified as the number of frames per second.
* `direction`: The direction of motion for the stream particles (e.g., `"down"`, `"up"`, `"left"`, `"right"`, `"diagonal-right"`, etc.).
* `stream_min_count`: The minimum number of entities per stream.
* `stream_max_count`: The maximum number of entities per stream.
* `stream_spacing`: The spacing between the streams, specified as the number of columns between each stream.
* `switch_interval`: The maximum number of seconds within which an entity randomly switches its symbol.

### Modes

The different modes available for the `mode` option are:

* "Original" | "Normal" | "Katakana": Original Katakana Symbols (e.g., ア, カ, サ, ナ)
* "Binary" | "Bin": 0s and 1s
* "Decimal" | "Numbers" | "Digits": Decimal numbers from 0 to 9
* "Math" | "Maths" | "Mathematics": Mathematical Symbols (e.g., ∐, ∑, ≠, →)
* "ASCII" | "Text" | "English": ASCII Characters (from '!' to '~', including A-Z, a-z, 0-9, etc.)
* "Braille" | "Dots": Braille patterns (e.g., ⠇, ⠾, ⣿)
* "Emoji" | "Cursed": Emojis
* Custom sets like "abc123": User-defined symbol set

### Customizing the Symbol Set

To specify custom character sets for the `mode` option, you can use the `Custom` variant of the `Symbols` enum.

Use the `--mode` option followed by your custom character set. For example, to use the custom character set "abc123", you would run the command:
```sh
cargo run --release -- --mode abc123
```

The custom character set can be any string of characters you want to use. The program will randomly select characters from this set for the matrix rain effect.

The custom character set is defined in the `src/config.rs` file and is handled by the `Symbols::Custom` variant in the `src/symbols.rs` file.

---

## Contributing

Contributions are welcome! If you would like to contribute to this project, please follow these guidelines:

1. Fork the repository and create a new branch for your feature or bugfix.
2. Write tests for your changes, if applicable.
3. Ensure that all tests pass and the code is properly formatted.
4. Submit a pull request with a clear description of your changes.

## License

This project is licensed under the [MIT License](./LICENSE). See the [`LICENSE`](./LICENSE) file for more information.
