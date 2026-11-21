<img src="assets/logo.png" width="112" height="112" alt="A ruddy turnstone levers a pebble with its short wedge-shaped bill.">

# Turnstone

Resume a chunked file job from acknowledged checkpoints. This Blyx workflow framework is part of the command-line tools collection.

A resumed batch can skip the final partial chunk when it treats a repeated acknowledgement as new progress. [Python, batching iterables](https://docs.python.org/3/library/itertools.html#itertools.batched)

## Editor extension

Install **RahulChaube.blyx-turnstone** to run the worked example and use the framework’s function completions in a Blyx file. Open an empty `.blyx` file, enter `blyx-turnstone-demo`, then choose **Blyx: Run File**. [Editor downloads](https://www.blyx-lang.space/packages/turnstone#editor) · [Download the extension](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-turnstone-0.1.0.vsix) · [Starter with framework source](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-turnstone-starter-0.1.0.zip)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-turnstone.git
cd blyx-turnstone
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-turnstone) · [Package page](https://www.blyx-lang.space/packages/turnstone) · [Handbook](https://doc.blyx-lang.space/guide/turnstone)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-turnstone.git vendor/turnstone
```

```blyx
use vendor::turnstone::turnstone;

fn main() {
    let size = 10.0;
    let width = 4.0;
    let checkpoints = [0, 0, 1];
    let result = turnstone_resume(size, width, checkpoints);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
8
2
1
1
```

## API

`turnstone_resume(size, width, checkpoints)`

Returns [next offset, byte count, remaining chunks, replayed checkpoints]. Offsets use half-open ranges. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| size | A nonnegative exact integer |
| width | A positive exact integer |
| checkpoints | Vector of values, each a nonnegative exact integer |

## Run the command-line project

Run the example with your own numbers. Vector arguments accept up to 16 comma-separated entries; use `[]` for an empty vector. The imported API accepts longer vectors. Invalid arguments return a nonzero exit status.

```sh
blyxc native-run project.blyx -- 10 4 "0,0,1"
```

## Libraries

- [ChunkSpan](https://github.com/Rahulchaube1/blyx-chunkspan/tree/v0.1.0) — Locate a fixed-width chunk including the final partial chunk.
- [ResumeIndex](https://github.com/Rahulchaube1/blyx-resumeindex/tree/v0.1.0) — Recover the first unfinished chunk from an ordered checkpoint log.

This release includes identical copies of both library modules so a tagged clone can build offline.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-turnstone/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The [artwork notice](assets/NOTICE.txt) records credits for earlier editions.

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
