# LLMCheckHelper

A Jupyter Notebook-based tool for automated academic paper analysis using Large Language Models (LLMs). This tool extracts content from LaTeX documents and performs multiple consistency and quality checks through the DeepSeek API.

## Features

- **LaTeX Content Extraction**: Parses LaTeX documents to extract meaningful content while handling commands, environments, and annotations
- **Structural Analysis**: Identifies deductive writing patterns (general-to-specific structures) in academic text
- **Grammar Checking**: Comprehensive English grammar, spelling, punctuation, and natural expression validation
- **Table-Paragraph Consistency**: Verifies consistency between tabular data and their textual descriptions
- **Section Hierarchy Mapping**: Builds document structure with section-subsection-paragraph relationships

## Requirements

- Python 3.10+
- OpenAI-compatible API client (configured for DeepSeek)
- LaTeX source document with standard structure

## Installation

1. Clone or download the notebook
2. Install required dependencies:
```bash
pip install openai tqdm
```

## Configuration

1. Set up your API credentials in `../localvariables/localvariables.json`:
```json
{
  "deepseek_api": "your_api_key_here"
}
```

2. Update the LaTeX file path in the notebook:
```python
tex_path = "../localvariables/your_paper.tex"
```

## Usage

1. Open `LLMCheckHelper.ipynb` in Jupyter Notebook
2. Run cells sequentially to:
   - Extract and preprocess LaTeX content
   - Build paragraph structure hierarchy
   - Initialize the LLM client
   - Perform various analysis checks

### Available Analysis Functions

- `check_deductive_structure()`: Analyzes paragraphs for general-to-specific writing patterns
- `check_grammar()`: Comprehensive grammar and language quality assessment
- `check_consistence_between_table_and_paragraph()`: Validates data consistency between tables and text

## Output

The tool generates detailed reports in the `./report/` directory:
- `deductive_structure.md`: Analysis of writing patterns
- `grammar.md`: Grammar and language quality assessment
- Additional consistency reports as generated

## Customization

The notebook can be easily modified to:
- Add new analysis types
- Adjust prompt engineering for different LLM behaviors
- Process different LaTeX document structures
- Integrate with other LLM APIs
