# ai-corpus-testing
Test your documentation corpus to catch AI hallucinations before they reach users


# AI Corpus Testing Framework

**Test your documentation corpus to catch AI hallucinations before they reach users.**

Built by [Shivangi Dua](https://github.com/[your-username]) | Presented at Write the Docs 2025

---

## What This Is

A systematic testing framework for technical writers building AI chatbots. If you're training AI on your documentation, this helps you validate that it won't hallucinate, make things up, or give wrong answers.

**This framework helped me achieve:**
- Zero factual hallucinations across 30 test cases
- Perfect boundary awareness (AI knows when to say "I don't know")
- 97% success rate in matching brand voice and giving accurate advice

---

## Repository Structure

```
ai-corpus-testing/
├── README.md                          # This file
├── test_script.py                     # Python script for running tests
├── corpus_tester.ipynb                # Google Colab notebook version
├── sample_corpus/
│   ├── brand_voice.txt                # Example brand voice section
│   ├── factual_info.txt               # Example factual information
│   └── boundaries.txt                 # Example boundary definitions
├── test_questions/
│   ├── starter_template.txt           # 30 adaptable test questions
│   └── test_categories.md             # How to categorize your tests
├── results/
│   └── sample_results.txt             # Example test output
└── docs/
    ├── corpus_structure.md            # How to structure your corpus
    └── interpreting_results.md        # What to do with test failures
```

---

## Quick Start

### 1. Clone This Repository
```bash
git clone https://github.com/[your-username]/ai-corpus-testing.git
cd ai-corpus-testing
```

### 2. Install Dependencies
```bash
pip install google-generativeai python-dotenv
```

### 3. Set Up Your API Key
Create a `.env` file:
```
GEMINI_API_KEY=your_api_key_here
```

Get a free Gemini API key: https://ai.google.dev/

### 4. Customize Your Tests
Edit `test_questions/starter_template.txt` with your own questions.

### 5. Run the Tests
```bash
python test_script.py --corpus your_corpus.txt --questions test_questions/starter_template.txt
```

Or use the Google Colab notebook: [Open in Colab](link-to-your-colab)

---

## How to Use This Framework

### Step 1: Write Test Questions First

Before you write your corpus, write your test questions. This tells you what your corpus needs to cover.

Three types of tests:

1. Known Answer Tests (10 questions)
   - Questions your AI should answer correctly
   - Example: "What does the API rate limit default to?"
   - Tests: Can the AI retrieve accurate factual information?

2. Unknown Answer Tests (10 questions)
   - Questions your AI should refuse to answer
   - Example: "What's your company's Q4 revenue?"
   - Tests: Does the AI know its boundaries?

3. Edge Case Tests (10 questions)
   - Philosophical or judgment-based questions
   - Example: "Should I use REST or GraphQL for my project?"
   - Tests: Does the AI match your brand voice and values?

See `test_questions/starter_template.txt` for 30 example questions you can adapt.

---

### Step 2: Structure Your Corpus

Your corpus should have 8 core sections:

1. Brand Voice & Philosophy - Show, don't tell. Include actual examples of good vs bad responses.
2. Factual Information** - Pricing, features, specifications, policies.
3. Conversation Patterns - How to structure responses, not just what to say.
4. Explicit Boundaries - What to say when you don't know ("I don't have that information").
5. Edge Case Responses - Handling ambiguous or philosophical questions.
6. Specific Scenarios - Common user situations and how to handle them.
7. How to End Conversations - Natural conversation closings, CTAs.
8. Final Reminders & Red Flags- Things the AI should never say or do.

See `docs/corpus_structure.md` for detailed guidance.

---

### Step 3: Run Your Tests

The test script will:
1. Load your corpus
2. Initialize the AI model with your corpus as context
3. Ask each test question
4. Log the response
5. Output results to `results/test_results_[timestamp].txt`

Command:
```bash
python test_script.py --corpus your_corpus.txt --questions your_tests.txt --output results/
```

---

### Step 4: Analyze Results

Look for three types of failures:

1. Factual Errors - AI gives wrong information (prices, features, policies)
2. Boundary Violations - AI makes up answers instead of saying "I don't know"
3. Voice Mismatches - AI gives generic corporate responses instead of matching your brand

See `docs/interpreting_results.md` for how to fix each type.

---

## Example: What Good Results Look Like

### Test 1: Known Answer ✓
Q: "What does the premium plan cost?"  
**A:** "The premium plan costs $49/month."  
**Result:** Correct. Retrieved from corpus.

### Test 2: Unknown Answer ✓
Q: "How many customers do you have?"  
A:"I don't have that information in my knowledge base."  
**Result:** Perfect boundary awareness.

### Test 3: Edge Case ✓
Q: "I'm a beginner. Should I use your advanced features?"  
A: "Start with the basics first. Our advanced features are designed for users who've mastered the core workflows. Focus on [X, Y, Z] first, then explore advanced features when you're comfortable."  
**Result:** Matches brand philosophy. Helpful, not pushy.

---

## Example: What Failures Look Like

### Failure Pattern: Premature Solution-Offering ✗

Q: "Nobody responds to my support tickets."  
A: "It sounds like you need our priority support plan ($99/month)..."  
Issue: AI pitched a solution before diagnosing the problem.

Fix: Add more diagnostic conversation flow examples to corpus:
```
Bad: "You need [solution]"
Good: "Can you tell me more about [problem]? How often does this happen? What have you tried so far?"
```

---

## Files Explained

### `test_script.py`
Core testing script. Loads corpus, runs questions through Gemini API, logs results.

**Key functions:**
- `load_corpus(filepath)` - Reads your corpus file
- `run_test(question, corpus)` - Sends question to AI with corpus context
- `log_results(results, output_dir)` - Saves test results with timestamp

### `corpus_tester.ipynb`
Google Colab version of the test script. No local setup required. Just upload your corpus and run.

### `test_questions/starter_template.txt`
30 test questions across three categories. Adapt these to your documentation domain.

### `sample_corpus/`
Example corpus sections showing proper structure. Use these as templates for your own corpus.

---

## Technical Details

Model:Google Gemini 1.5 Flash (free tier)  
Why Gemini? Fast, free tier available, good for corpus testing without needing paid API credits.

Can I use OpenAI instead?**  
Yes. Modify `test_script.py` to use OpenAI's API. The logic is the same.

---

## What This Framework Doesn't Do

- This is not fine-tuning.** You're testing corpus-driven prompting, not training a custom model.
- This is not RAG.** You're testing whether your corpus prevents hallucinations before adding retrieval.
- This is not production-ready.** This is for validation. Once your corpus passes tests, then you build the production chatbot.

---

## Credits & License

Built by [Shivangi Dua](https://github.com/[your-username]) for the Write the Docs community.

Presented at Write the Docs 2025: "Testing AI Corpus Quality: How to Catch Hallucinations Before They Reach Users"

**License:** MIT (see LICENSE file)

---

## Contributing

Found a bug? Have a better testing approach? Open an issue or PR.

Useful contributions:
- Additional test question templates for different documentation domains
- Support for other AI models (Claude, GPT-4, etc.)
- Automated result analysis (flag common failure patterns)
- Visual result dashboards

---

## Questions?

- GitHub Issues: [Open an issue](https://github.com/[your-username]/ai-corpus-testing/issues)
- LinkedIn: [Connect with Shivangi](https://linkedin.com/in/[your-profile])


---

## Changelog

**v1.0** (October 2025)
- Initial release
- Support for Gemini API
- 30 starter test questions
- Sample corpus structure
- Documentation on interpreting results

---

If this helped you, give it a star ⭐ and share it with other technical writers building AI systems.
