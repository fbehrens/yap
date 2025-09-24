## Project Overview

This project, `yap`, is a command-line interface (CLI) tool for macOS that provides on-device speech transcription. It is written in Swift and utilizes Apple's `Speech.framework` to perform transcriptions locally.

The tool can take an audio or video file as input and output the transcription in either plain text (`.txt`) or SubRip Subtitle (`.srt`) format. It supports multiple locales and can automatically download necessary language assets.

The project is structured as a Swift package and uses `swift-argument-parser` to define and handle command-line arguments. The `Noora` library is used for displaying progress bars and other CLI UI elements.

## Building and Running

As a standard Swift package, the project can be built and run using the following commands from the project root directory:

*   **Build the project:**
    ```bash
    swift build
    ```

*   **Run the application:**
    ```bash
    swift run yap <subcommand> [options]
    ```

    For example, to transcribe a file:
    ```bash
    swift run yap transcribe path/to/audio.mp4 --srt --output-file captions.srt
    ```

## Development Conventions

*   **Command-Line Interface:** The CLI is built using `swift-argument-parser`. The main command is `Yap`, with `Transcribe` as the default subcommand.
*   **Dependencies:** Key dependencies include `swift-argument-parser` for the CLI structure and `Noora` for interactive elements like progress bars.
*   **Code Style:** The project uses `.swiftformat` to enforce a consistent code style. The configuration is defined in the `.swiftformat` file at the root of the project.
*   **Modularity:** The core logic is separated into different files based on functionality:
    *   `Yap.swift`: The main entry point for the CLI application.
    *   `Transcribe.swift`: Contains the primary logic for the transcription process.
    *   `OutputFormat.swift`: Handles the formatting of the transcription into different output types (`txt`, `srt`).
    *   `Extensions/`: Contains extensions to standard library types to support the application's functionality.
