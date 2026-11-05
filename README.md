# llm-hack
Using LLMs to hunt for vulnerabilities.

## Concepts
### Harness 
The thing that sends request to the model.

- Pi: https://pi.dev/
- OpenCode: https://opencode.ai/

### Static Analysis
Reason about all the code, without running it. For humans, this is reading.
```

   SOURCE CODE         INSPECT
  +------------+        _____
  | if (x > 0) |       /     \
  |   foo(x);  |------(  ? !  )
  | return 0;  |       \_____/
  +------------+          |
                          |
```

- A decompiler: https://github.com/bethington/ghidra-mcp, https://github.com/noelo-lab/kuna
- A query engine: https://codeql.github.com/, https://github.com/joernio/joern
- Other tools: https://tree-sitter.github.io/tree-sitter/, https://docs.angr.io/en/v9.3.3/api/angr.mcp.html

### Dynamic Analysis
Reason about one segment of code, by running. For humans, this is a debugger.

```
   RUNNING PROGRAM       OBSERVE
  +----------------+    +-----------+
  |  > ./program   |--->| CPU  /\/\ |
  |  [ RUNNING ▶ ] |    | MEM  _/-- |
  |  input -> out  |    | LOG  ...  |
  +----------------+    +-----------+
```

- Scripting for tracing:  https://github.com/qilingframework/qiling, https://frida.re/
- Emulation: https://www.qemu.org/
- Debugging: https://github.com/Ipiano/gdb-mcp

### Strategies

- Look for bugs where they have already been found. 

## Example Target:
https://github.com/mahaloz/vulnet-ctf-challenge
