## Restart an interrupted chunked file job

Returns [next offset, byte count, remaining chunks, replayed checkpoints]. Offsets use half-open ranges. Invalid arguments and nonfinite results return an empty vector.

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

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-turnstone)
