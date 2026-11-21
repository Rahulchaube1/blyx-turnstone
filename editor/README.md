# Blyx Turnstone

Resume a chunked file job from acknowledged checkpoints.

This extension includes the Blyx Turnstone 0.1.0 source, a runnable example and completions for its public functions. It uses the Blyx Language extension for syntax highlighting and execution.

## Run in the editor

1. Open an empty file named `turnstone-demo.blyx`.
2. Type `blyx-turnstone-demo` and select **Turnstone — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
8
2
1
1
```

## Use Turnstone in a project

Extract the starter into a new folder. It contains `main.blyx`, the licensed framework source in `vendor/turnstone`, and a VS Code task. With the Blyx 0.2.1 compiler and host toolchain installed, run `blyxc native-run main.blyx` from that folder. Type `blyx-turnstone-` in a Blyx file to see the framework completions. [Download the starter ZIP](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-turnstone-starter-0.1.0.zip)

[API and input requirements](https://www.blyx-lang.space/packages/turnstone) · [Framework source](https://github.com/Rahulchaube1/blyx-turnstone/tree/bb5e14660a3e17c10fc10565d39aa0976154adf7) · [Report an issue](https://github.com/Rahulchaube1/blyx-turnstone/issues)

[GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) · [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube)
