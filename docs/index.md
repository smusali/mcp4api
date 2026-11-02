# mcp4api

mcp4api turns your API docs into a working MCP server, then calls every generated
tool against your API and reports which ones work. The repository is
[smusali/mcp4api](https://github.com/smusali/mcp4api).

Built for platform teams who want their product callable by agents.

## Install

```bash
pip install mcp4api
uvx mcp4api
```

## Quickstart

These commands need no API key. They reuse the committed manifest and cassettes,
regenerate the other artifacts in place, and exit 3. The sample's one known gap
is `get_book`: `page_count` is a string in the API and an integer in the spec.

```bash
git clone https://github.com/smusali/mcp4api && cd mcp4api
uvx mcp4api examples/sample-api/openapi.yaml --offline --out examples/sample-api
cat examples/sample-api/report/verification.md
```

![Offline run against the Shelf sample, from ingest through the verification summary](https://raw.githubusercontent.com/smusali/mcp4api/main/examples/demo.gif)

![Verification report for the Shelf sample, with get_book as the known gap](https://raw.githubusercontent.com/smusali/mcp4api/main/examples/verification.png)

Where to go next:

- [Usage](USAGE.md) for every command, flag, and exit code.
- [Architecture](ARCHITECTURE.md) for the four-stage pipeline.
- [Methodology](METHODOLOGY.md) for curation and verification.
- [Limitations](limitations.md) for what mcp4api does not do.
