# Neurosymblic Examples 

This repository contains some minimal working examples leveraging Python and Lean to implement 
the "verified checker" pattern, as described in the UT Austin fall 2026 COE 379L course offering.
Over time, additional examples and patterns may be added. 

The examples are driven by a CLI. Pass JSON presenting a `Claim` as would be produced by the AI
subsystem. The Python code invokes a compiled Lean checker as a subprocess. The Lean program 
decodes the JSON to a `Claim` term, verifies the citation policy against the pre-built manifest, and
returns a JSON Boolean. The Python application reads the JSON and proceeds only if Lean explicitly 
returns a valid `{"allowed": true}` response.

Note: This is an educational repository. 


## Building the code

This project reqiures Lean and Lake (but not Mathlib, for now). It also needs Python 3.11+. 

1. Build the Lean: 

```bash
lake build
```

2. Build the Python env: 

```bash 
uv sync
```

## Trying the examples 

Use `uv` to execute the Python CLI. There are some examples in the `examples` directory. 

```bash 
uv run python -m ns_skeleton.cli --example good_proved_result
