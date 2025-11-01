# ai-corpus-testing
Test your documentation corpus to catch AI hallucinations before they reach users


# AI Corpus Testing Framework

Test your documentation corpus to catch AI hallucinations before they reach users.

Built by [Shivangi Dua](https://github.com/[your-username]) | Presented at Write the Docs 2025

---

What This Is

A systematic testing framework for technical writers building AI chatbots. If you're training AI on your documentation, this helps you validate that it won't hallucinate, make things up, or give wrong answers.
This framework helped me achieve:
- Zero factual hallucinations across 30 test cases
- Perfect boundary awareness (AI knows when to say "I don't know")
- 97% success rate in matching brand voice and giving accurate advice

---
 Repository Structure

```
ai-corpus-testing/
├── README.md                          # This file
├── ai_corpus_tester.ipynb                # Google Colab notebook version
├── docs/
    ├── brand_voice.txt                # Example brand voice section
    ├── factual_info.txt               # Example factual information
    └── boundaries.txt                 # Example boundary definitions
    ├── corpus_structure.md            # How to structure your corpus
    


├── test_questions/
│   ├── starter_template.txt           # 30 adaptable test questions
│   └── test_categories.md             # How to categorize your tests



---

 Quick Start

 1. Clone This Repository

git clone https://github.com/shivangiduaa/ai-corpus-testing.git
cd ai-corpus-testing
```

 

Get a free Gemini API key: https://ai.google.dev/

 

Use the Google Colab notebook: 

---

How to Use This Framework

Step 1: Write Test Questions First

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

Step 2: Structure Your Corpus

Your corpus should have 8 core sections:

1. Brand Voice & Philosophy - Show, don't tell. Include actual examples of good vs bad responses.
2. Factual Information - Pricing, features, specifications, policies.
3. Conversation Patterns - How to structure responses, not just what to say.
4. Explicit Boundaries - What to say when you don't know ("I don't have that information").
5. Edge Case Responses - Handling ambiguous or philosophical questions.
6. Specific Scenarios - Common user situations and how to handle them.
7. How to End Conversations - Natural conversation closings, CTAs.
8. Final Reminders & Red Flags- Things the AI should never say or do.

See docs/corpus_structure.md for detailed guidance.

---

 Step 3: Run Your Tests



 Step 4: Analyze Results

Look for three types of failures:

1. Factual Errors - AI gives wrong information (prices, features, policies)
2. Boundary Violations - AI makes up answers instead of saying "I don't know"
3. Voice Mismatches - AI gives generic corporate responses instead of matching your brand



---

 Example: What Good Results Look Like

Test 1: Known Answer ✓
Q: "What does the premium plan cost?"  
A:"The premium plan costs $49/month."  
Result:Correct. Retrieved from corpus.

Test 2: Unknown Answer ✓
Q: "How many customers do you have?"  
A:"I don't have that information in my knowledge base."  
Result: Perfect boundary awareness.

 Test 3: Edge Case ✓
Q: "I'm a beginner. Should I use your advanced features?"  
A: "Start with the basics first. Our advanced features are designed for users who've mastered the core workflows. Focus on [X, Y, Z] first, then explore advanced features when you're comfortable."  
Result: Matches brand philosophy. Helpful, not pushy.

---

 Example: What Failures Look Like

 Failure Pattern: Premature Solution-Offering ✗

Q: "Nobody responds to my support tickets."  
A: "It sounds like you need our priority support plan ($99/month)..."  
Issue: AI pitched a solution before diagnosing the problem.

Fix: Add more diagnostic conversation flow examples to corpus:

Bad: "You need [solution]"
Good: "Can you tell me more about [problem]? How often does this happen? What have you tried so far?"


---

 Files Explained

ai_corpus_tester.ipynb
Google Colab version of the test script. No local setup required. Just upload your corpus and run.

test_questions/starter_template.txt
30 test questions across three categories. Adapt these to your documentation domain.


Technical Details

Model:Google Gemini 2.0 Flash (free tier)  
Why Gemini? Fast, free tier available, good for corpus testing without needing paid API credits.

Can I use OpenAI instead? 
Yes. Modify  to use OpenAI's API. The logic is the same.

---

What This Framework Doesn't Do

- This is not fine-tuning. You're testing corpus-driven prompting, not training a custom model.
- This is not RAG. You're testing whether your corpus prevents hallucinations before adding retrieval.
- This is not production-ready. This is for validation. Once your corpus passes tests, then you build the production chatbot.

---

Credits & License

Built by Shivangi Dua for the Write the Docs community.

Presented at Write the Docs 2025: "Testing AI Corpus Quality: How to Catch Hallucinations Before They Reach Users"

License: MIT (see LICENSE file)

---

Contributing

Found a bug? Have a better testing approach? Open an issue or PR.

Useful contributions:
- Additional test question templates for different documentation domains
- Support for other AI models (Claude, GPT-4, etc.)
- Automated result analysis (flag common failure patterns)
- Visual result dashboards

---

 Questions?

- GitHub Issues: [Open an issue](https://github.com/[your-username]/ai-corpus-testing/issues)
- LinkedIn: [Connect with Shivangi](https://linkedin.com/in/[your-profile])


---
Changelog

v1.0 (October 2025)
- Initial release
- Support for Gemini API
- 30 starter test questions
- Sample corpus structure
- Documentation on interpreting results

---

If this helped you, give it a star ⭐ and share it with other technical writers building AI systems.
