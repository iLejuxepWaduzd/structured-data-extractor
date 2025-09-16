# Structured Data Extractor
This project demonstrates how Chain-of-Thought prompting and structured output formatting can extract consistent data from messy text inputs. The system processes customer support messages, app reviews, and support tickets to identify key information about technical issues.

## Technical Approach
The extraction uses a two-step reasoning process:
1. First, it analyzes the text to identify different elements like error messages, timestamps, and technical details
2. Then, it maps these elements to a predefined JSON schema with consistent field names

The prompt engineering incorporates:
- Explicit step-by-step reasoning instructions (Chain-of-Thought)
- Strict output formatting requirements
- Handling of missing information with default values
- Severity classification based on described impact

## Challenges with Unstructured Data
The input texts present several extraction challenges:
- Inconsistent mention of technical details
- Varied descriptions of the same problem
- Mixed severity indicators within narratives
- Implicit rather than explicit information

The Chain-of-Thought approach addresses these by forcing the model to explicitly reason about each element before extraction, significantly improving accuracy over direct extraction prompts.

## Results
The technique successfully converted all test cases into properly formatted JSON with appropriate field mapping. The structured output enables:
- Automated ticket routing based on component and severity
- Consistent data for analytics and reporting
- Integration with downstream systems
- Trend analysis across support requests

## 📁Project Structure
```
structured-data-extractor/
├── inputs/ # Raw unstructured text samples
├── outputs/ # Extracted structured JSON data
├── prompts/ # Engineered prompt template
└── README.md # Project documentation
```


## Usage
The prompt template can be adapted for various extraction tasks by modifying the field definitions and reasoning steps. The approach works best when the target schema remains consistent across extraction tasks.