# Installation Guide

This guide will walk you through installing NeMo Guardrails, and it will cover:

1. Setting up a fresh virtual environment.
2. Installing using `pip`.
3. Installing from Source Code.
4. Optional dependencies.

## Prerequisites

Python 3.8+.

## Additional dependencies

NeMo Guardrails uses [annoy](https://github.com/spotify/annoy), which is a C++ library with Python bindings. To install it, you need to have a valid C++ runtime on your computer.
Most systems already have installed a C++ runtime. If `annoy` installation fails, check the following steps:

- For a Linux or Mac / Unix-based OS:
  - First install `gcc` and `g++` using `apt-get install gcc g++`.
  - Then update the following environment variables: `export CC=<path_to_clang>` and `export CXX=<path_to_clang++>` (usually, `<path_to_clang>` is `/usr/bin/clang`).
- For Windows:
  - Install [Microsoft C++ Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/). This should install Microsoft Visual C++ (version 14.0 or greater is required by latest version of `annoy`).

## Setting up a virtual environment

If you want to experiment with NeMo Guardrails from scratch, we recommend using a fresh virtual environment. Otherwise, you can skip to the following subsection.

1. First, create a folder for your project, e.g., `my_assistant.`

 ```bash
 > mkdir my_assistant
 > cd my_assistant
 ```

2. Create a virtual environment.

 ```bash
 > python3 -m venv venv
 ```

3. Activate the virtual environment.

 ```bash
 > source venv/bin/activate
 ```

## Installation using `pip`

To install NeMo Guardrails using pip:

 ```bash
 > pip install nemoguardrails
 ```

## Installing from source code

NeMo Guardrails is under active development and the main branch will always contain the latest development version. To install from source, you first need to clone the repository:

```
git clone https://github.com/NVIDIA/NeMo-Guardrails.git
```

Next, you need to install the package locally:

```
cd NeMo-Guardrails
pip install -e .
```

## Optional dependencies

If you want to use OpenAI, also install the `openai` package with the latest version supported by Nemo Guardrails as shown below.
And make sure that you have the `OPENAI_API_KEY` environment variable set.

 ```bash
 > pip install openai==0.28.1
 > export OPENAI_API_KEY=...
 ```

Some NeMo Guardrails LLMs and features have specific installation requirements, including a more complex set of steps (e.g. [AlignScore](../user_guides/advanced/align_score_deployment.md) fact-checking, using [Llama-2](../../examples/configs/llm/hf_pipeline_llama2/README.md)).
For each feature or LLM example, check the readme files associated with it.

## Extra dependencies

The following extra dependencies are defined:
- `dev`: packages required by some extra Guardrails features for developers (e.g. autoreload feature).
- `eval`: packages used for the Guardrails [evaluation tools](../../nemoguardrails/eval/README.md).
- `openai`: installs the latest `openai` package supported by NeMo Guardrails.
- `sdd`: packages used by the [sensitive data detector](../user_guides/guardrails-library.md#sensitive-data-detection) integrated in NeMo Guardrails.
- `all`: installs all extra packages.

## What's next?

* Check out the [Getting Started Guide](../getting_started) and start with the ["Hello World" example](../getting_started/1_hello_world).
* Explore more examples in the [examples](../../examples) folder.
* Review the [User Guides](../user_guides).
