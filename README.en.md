# Conversational AI Benchmark Cases

A comprehensive collection of benchmark test cases for evaluating Text-to-Speech (TTS) systems and conversational AI models across multiple languages and scenarios.

## Overview

This repository contains carefully curated test cases designed to evaluate the performance of TTS systems and conversational AI models on various linguistic challenges, including pronunciation accuracy, punctuation handling, technical terminology, and multilingual processing.

## Repository Structure

```
├── TTS_AP/                    # Text-to-Speech Accuracy & Pronunciation
│   ├── en/                    # English test cases
│   │   ├── abbreviations_acronyms.csv
│   │   ├── complex_combinations.csv
│   │   ├── punctuation_formatting.csv
│   │   └── special_cases.csv
│   └── zh/                    # Chinese test cases
│       ├── abbreviations_technical_terms.csv
│       ├── composite_combination.csv
│       ├── digital_processing.csv
│       ├── polyphonic_character.csv
│       └── punctuation_formatting.csv
├── TTS_WER/                   # Word Error Rate evaluation
│   ├── general_en.csv
│   └── general_zh.csv
└── LICENSE
```

## Test Case Categories

### TTS_AP (Text-to-Speech Accuracy & Pronunciation)

#### English Test Cases (`TTS_AP/en/`)
- **abbreviations_acronyms.csv**: Technical abbreviations, acronyms, and units (e.g., "3.7 m/s²" → "three point seven meters per second squared")
- **complex_combinations.csv**: Complex linguistic combinations and edge cases
- **punctuation_formatting.csv**: URL formatting, special characters, and punctuation handling
- **special_cases.csv**: Special pronunciation cases and exceptions

#### Chinese Test Cases (`TTS_AP/zh/`)
- **abbreviations_technical_terms.csv**: Technical terms, codes, and abbreviations (e.g., "JSYH23001" → "JSYH二三零零幺")
- **composite_combination.csv**: Complex Chinese character combinations
- **digital_processing.csv**: Number and unit processing in Chinese context
- **polyphonic_character.csv**: Polyphonic characters with different pronunciations
- **punctuation_formatting.csv**: Chinese punctuation and formatting rules

### TTS_WER (Word Error Rate)

- **general_en.csv**: General English conversational text for WER evaluation
- **general_zh.csv**: General Chinese conversational text for WER evaluation

## Data Format

All CSV files follow a consistent format:
- **Column 1**: `Sample Text` / `测试文本` - Input text for TTS processing
- **Column 2**: `Expected Output` / `应正确读出的文本` - Expected pronunciation output

## Usage

### For TTS System Evaluation

1. **Pronunciation Accuracy Testing**:
   ```python
   import pandas as pd

   # Load test cases
   test_cases = pd.read_csv('TTS_AP/en/abbreviations_acronyms.csv')

   # Process with your TTS system
   for _, row in test_cases.iterrows():
       input_text = row['Sample Text']
       expected = row['Expected Output']
       actual = your_tts_system.synthesize(input_text)
       # Compare actual vs expected
   ```

2. **Word Error Rate Calculation**:
   ```python
   # Load WER test cases
   wer_cases = pd.read_csv('TTS_WER/general_en.csv')

   # Calculate WER for conversational text
   for _, row in wer_cases.iterrows():
       reference = row['Expected Output']
       hypothesis = your_tts_system.synthesize(row['Sample Text'])
       wer = calculate_wer(reference, hypothesis)
   ```

### For Model Benchmarking

Use these test cases to:
- Evaluate pronunciation accuracy across different linguistic domains
- Test handling of technical terminology and abbreviations
- Assess multilingual capabilities
- Measure word error rates in conversational contexts
- Compare different TTS models and configurations

## Key Features

- **Multilingual Support**: Comprehensive test cases for English and Chinese
- **Domain Coverage**: Technical, conversational, and specialized vocabulary
- **Real-world Scenarios**: Practical examples from various domains
- **Standardized Format**: Consistent CSV format for easy integration
- **Comprehensive Coverage**: Edge cases, abbreviations, numbers, and special characters

## Contributing

This benchmark collection is maintained by the Shengwang Community. Contributions are welcome for:
- Additional test cases
- New language support
- Improved test coverage
- Bug fixes and corrections

## License

This project is licensed under the terms specified in the LICENSE file.

## Citation

If you use this benchmark in your research or development, please cite:

```bibtex
@misc{conversational_ai_benchmark,
  title={Conversational AI Benchmark Cases},
  author={Shengwang Community},
  year={2024},
  url={https://github.com/Shengwang-Community/Conversational-AI-Benchmark-cases}
}
```

## Contact

For questions, suggestions, or contributions, please open an issue in this repository or contact the Shengwang Community.
