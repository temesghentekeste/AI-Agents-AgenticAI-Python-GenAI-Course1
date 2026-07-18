# AI-Agents-AgenticAI-Python-GenAI-Course1

## Overview
This repository contains implementations for building intelligent systems using Agentic AI workflows. The core project uses a multi-turn, sequential prompting pipeline to dynamically generate, document, and test clean Python code.

## Projects
*   **QuasiAgent.ipynb**: An interactive Jupyter Notebook implementation that acts as a code-generation agent. It leverages a three-stage prompting structure to transition a basic user request into an enterprise-ready script complete with standard `unittest` cases and thorough documentation.

## Architecture Workflow
The sequential execution pipeline, state management, and memory tracking structure of the project are visualized in the architectural blueprint below:

![QuasiAgent Flowchart](https://gemini.google.com/share/afb54c01d410?skid=3aae8ff0-7418-480d-8af7-351fc97490ce)

---

## 1. Implementation Architecture

The agent functions through an iterative context-accumulation loop:

1.  **Phase 1 (The Logic Blueprint):** Captures user intent and leverages an LLM running at a deterministic low temperature (`0.2`) to output a raw python code block.
2.  **Phase 2 (Hardening & Documentation):** Feeds the memory state back to the LLM to inject descriptive docstrings, parameter definitions, and edge-case exceptions.
3.  **Phase 3 (Unit Testing Verification):** Appends standard Python `unittest.TestCase` configurations directly underneath the module execution environment.

A specialized regular expression parser (`extract_code`) handles post-processing, filtering away arbitrary chat commentary to isolate the functional program.

## 2. Running the Agent (Google Colab / Cloud Environments)

You can execute `QuasiAgent.ipynb` directly inside a cloud workstation instance (like Google Colab) without external dependencies:

*   **Runtime I/O:** The execution loop leverages standard virtual machine inputs to take parameters seamlessly within browser interfaces.
*   **Terminal Native Checking:** To execute and immediately evaluate the generated test suites from your virtual workspace, use bash integration syntax directly inside a notebook cell block:
    ```bash
    !python generated_function.py
    ```
