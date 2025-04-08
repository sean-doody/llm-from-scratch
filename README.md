# Building a GPT-Style LLM From Scratch

This repository contains my notes, code, and implementation of a GPT-like LLM, based on Sebastian Rashchka's book, *Build a Large Language Model (From Scratch)*. The repo will be updated as I work through the chapters.

## Environment

[uv](https://github.com/astral-sh) is used for virtual environment management:

```
uv venv --python 3.11
source .venv/bin/activate
uv pip install -r requirements.txt
```

Free GPU compute from [Lightning AI](https://lightning.ai/) was used to perform the instruction fine-tune using the `355M` GPT-2 model from chapter 7.

To get Ollama up and running for the Ch. 7 evaluation:

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

I also had to change the port on my Lightning AI VM:

```bash
OLLAMA_HOST=127.0.0.1:8080 ollama serve
```

## The Book

Raschka, Sebastian. 2025. *Build a Large Language Model (From Scratch).* Shelter Island, NY: Manning.

[Amazon](https://www.amazon.com/Build-Large-Language-Model-Scratch/dp/1633437167) | [Publisher](https://www.manning.com/books/build-a-large-language-model-from-scratch)