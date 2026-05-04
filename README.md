# ITPM Assignment 1 - Transliteration Accuracy Testing

**Student ID:** IT23679894  
**Module:** IT3040 – ITPM  
**Option:** Option 1 – For students familiar with Sinhala  

## Objective

This assignment evaluates the correctness of the **Chat Sinhala transliteration** function available at:  
🔗 [https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator)

The application converts **chat-style Singlish** input into **Sinhala** output. This project identifies **50 test cases** where the system **fails** to correctly convert Singlish to Sinhala, covering **25 different Singlish input types**.

## Test Cases

All 50 test cases are documented in the Excel file: `IT23679894.xlsx`

### Input Types Covered (25 types, 2 test cases each)

| # | Input Type | # | Input Type |
|---|------------|---|------------|
| 1 | Phonetic | 14 | Negation |
| 2 | Repeated | 15 | Question |
| 3 | Missing vowels | 16 | Continuous |
| 4 | Slang | 17 | Pronouns |
| 5 | English mix | 18 | Particles |
| 6 | Abbreviation | 19 | English sound |
| 7 | Numbers | 20 | Contraction |
| 8 | Homophones | 21 | Mixed grammar |
| 9 | Spacing | 22 | Extra |
| 10 | Capitalization | 23 | Dialect |
| 11 | Punctuation | 24 | Word order |
| 12 | Elongation | 25 | Typos |
| 13 | Double meaning | | |

## Test Automation

All test cases are automated using **Playwright** (Python). The automation script:
1. Opens the transliteration website
2. Types each Singlish input into the input textarea
3. Clicks the "Transliterate" button
4. Captures the actual Sinhala output
5. Compares it with the expected output
6. Records the result (Pass/Fail) in the Excel file

## How to Run

### Prerequisites
- Python 3.10 or higher
- Google Chrome (recommended) or Chromium

### Setup

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Install Playwright browsers:**
   ```bash
   python -m playwright install chromium
   ```

### Run the Tests

```bash
python test_automation.py --excel IT23679894.xlsx --sheet "Test Cases"
```

#### Additional Options:
```bash
# Run in headless mode (no browser window)
python test_automation.py --excel IT23679894.xlsx --sheet "Test Cases" --headless

# Keep browser open after tests
python test_automation.py --excel IT23679894.xlsx --sheet "Test Cases" --keep-open

# Save results after every test
python test_automation.py --excel IT23679894.xlsx --sheet "Test Cases" --save-every 1
```

## Project Structure

```
ITPM_Assignment1/
├── IT23679894.xlsx          # Test cases with results
├── test_automation.py       # Playwright automation script
├── requirements.txt         # Python dependencies
└── README.md                # This file
```

## Results Summary

- **Total Test Cases:** 50
- **Pass:** 0
- **Fail:** 50
- All test cases represent scenarios where the transliteration system fails to produce the correct Sinhala output.
