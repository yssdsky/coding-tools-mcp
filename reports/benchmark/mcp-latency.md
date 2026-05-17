# MCP Runtime Latency Benchmark

- Conclusion: **PASS**
- Endpoint: `http://127.0.0.1:38489/mcp`
- Iterations: `8`
- Exec iterations: `4`
- Warmup iterations: `2`
- Max MCP p95 threshold: `5000 ms`

## Metrics

| metric | samples | min ms | p50 ms | p95 ms | max ms |
| --- | ---: | ---: | ---: | ---: | ---: |
| `mcp.tools_list` | 8 | 1.06 | 1.105 | 1.153 | 1.156 |
| `mcp.read_file` | 8 | 0.695 | 0.749 | 0.781 | 0.786 |
| `mcp.search_text` | 8 | 57.91 | 58.48 | 64.569 | 66.713 |
| `mcp.exec_command` | 4 | 46.787 | 47.428 | 48.128 | 48.173 |
| `native.read_text` | 8 | 0.028 | 0.029 | 0.03 | 0.03 |
| `native.search` | 8 | 3.92 | 4.44 | 4.667 | 4.692 |
| `native.exec_python` | 4 | 24.011 | 24.67 | 26.58 | 26.855 |

## Native Baseline Comparison

| operation | MCP p95 ms | native p95 ms | ratio |
| --- | ---: | ---: | ---: |
| `read_file` | 0.781 | 0.03 | 26.033 |
| `search_text` | 64.569 | 4.667 | 13.835 |
| `exec_command` | 48.128 | 26.58 | 1.811 |

## Failures

No failures recorded.

## Notes

- Native baselines are local developer-tool primitives, not equivalent MCP substitutes.
- Latency thresholds are intentionally broad; this smoke benchmark catches transport regressions and records trend evidence.
