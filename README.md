# gptpdf
Using GPT to parse PDF

## Introduction

This package uses OpenAI's GPT-4o to parse PDFs to Markdowns.
It perfectly parse text, image, math equations, charts, and tables.
It almost cost $0.013 per page.


## DEMO

See [examples/attention_is_all_you_need/output.md](examples/attention_is_all_you_need/output.md)

## Installation

```bash
pip install gptpdf
```

## Usage

```python
from gptpdf import parse_pdf
pdf_path = '../examples/attention_is_all_you_need.pdf'
output_dir = '../examples/attention_is_all_you_need/'
api_key = os.getenv('OPENAI_API_KEY')
base_url = os.getenv('OPENAI_API_BASE')
# Manually provide OPENAI_API_KEY and OPEN_API_BASE
content, image_paths = parse_pdf(pdf_path, output_dir=output_dir, api_key=api_key, base_url=base_url, model='gpt-4o')
print(content)
print(image_paths)
# also output_dir/output.md is generated
```

```python
from gptpdf import parse_pdf
pdf_path = '../examples/attention_is_all_you_need.pdf'
output_dir = '../examples/attention_is_all_you_need/'
# Use OPENAI_API_KEY and OPENAI_API_BASE from environment variables
content, image_paths = parse_pdf(pdf_path, output_dir=output_dir, model='gpt-4o', verbose=True)
print(content)
print(image_paths)
# also output_dir/output.md is generated
```