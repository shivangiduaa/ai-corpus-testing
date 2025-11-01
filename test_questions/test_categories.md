# Test Question Categories

How to categorize your test questions and what each category tells you about your corpus.

---

## Category 1: Known Answer Tests

### What They Test
Whether the AI can accurately retrieve factual information from your corpus.

### When to Use
For any question that has ONE correct answer that exists in your corpus.

### Examples
- "How much does [product] cost?"
- "What features are included in [plan]?"
- "How many sessions are in [workshop]?"
- "What's the difference between [option A] and [option B]?"
- "What platforms is [product] available on?"

### What Success Looks Like
The AI gives the EXACT information from your corpus. Word-for-word isn't necessary, but the facts must be accurate.

**Good response:**
```
Q: "How much does the Pro plan cost?"
A: "The Pro plan costs $49/month."
```

**Bad response:**
```
Q: "How much does the Pro plan cost?"
A: "The Pro plan is competitively priced for growing teams. Contact sales for details."
```
(Vague, doesn't give the price)

### What Failure Means
- The information isn't in your corpus → Add it
- The information is buried or ambiguous → Make it more prominent and explicit
- The information is contradictory → Consolidate into one canonical answer

---

## Category 2: Unknown Answer Tests

### What They Test
Whether the AI knows its boundaries and says "I don't know" when appropriate.

### When to Use
For questions about information you deliberately DIDN'T include in the corpus.

### Examples
- "What's your company's annual revenue?"
- "How many customers do you have?"
- "What's your refund policy?" (if you haven't documented it)
- "Do you offer [service you don't offer]?"
- "How does your product compare to [competitor]?"

### What Success Looks Like
The AI explicitly says it doesn't have that information.

Good response:**

Q: "What's your annual revenue?"
A: "I don't have that information in my knowledge base."


**Bad response:**
```
Q: "What's your annual revenue?"
A: "We're a growing company with increasing revenue year over year."
```
(Made up information, avoided saying "I don't know")

### What Failure Means
- Your boundaries aren't explicit enough → Add a "Boundaries" section
- You didn't list what topics the AI should refuse → Be more specific
- The AI is trying to be helpful by guessing → Reinforce "say I don't know" in corpus

---

## Category 3: Edge Case Tests

### What They Test
Whether the AI matches your brand philosophy, voice, and values when there's no single "correct" answer.

### When to Use
For philosophical, emotional, or ambiguous questions where the response quality matters more than factual accuracy.

### Examples
- "I've tried [approach] and it didn't work. Help?"
- "I'm scared to [take action]. What do you think?"
- "Should I [do option A] or [do option B]?"
- "I'm a [specific user type] with [specific constraint]. What should I do?"
- "Nobody responds to my [outreach/application]. What am I doing wrong?"


## How to Write Good Test Questions

### For Known Answer Tests:

✓ DO:
- Ask for specific facts (prices, features, timelines)
- Use clear, direct phrasing
- Ask about information you KNOW is in the corpus

✗ DON'T:
- Ask questions with multiple valid answers
- Use ambiguous phrasing ("around how much," "typically")
- Test for information that's implied but not stated

### For Unknown Answer Tests:

✓ DO:
- Ask about information you deliberately excluded
- Test internal company data (revenue, team size)
- Ask about policies you haven't documented

✗ DON'T:
- Ask about things the AI might reasonably infer
- Test with questions that have partial information in the corpus
- Expect the AI to refuse questions about tangentially related topics

### For Edge Case Tests:

✓ DO:
- Include emotional language ("I'm scared," "I'm frustrated")
- Test philosophical or judgment-based questions
- Ask about specific user scenarios

✗ DON'T:
- Write trick questions designed to trap the AI
- Test with scenarios so rare they're not worth handling
- Expect perfect answers—you're testing tone and approach, not facts

---

## Balancing Your Test Suite

### Recommended Distribution:
- **10 Known Answer Tests** (33%)
- **10 Unknown Answer Tests** (33%)
- **10 Edge Case Tests** (33%)

### Why This Balance?
- **Known Answer Tests** catch factual errors and missing information
- **Unknown Answer Tests** catch hallucinations and boundary violations
- **Edge Case Tests** catch voice mismatches and philosophy gaps

If you only test one category, you'll miss critical failure patterns.

---

## Expanding Your Test Suite

Start with 30 tests (10 per category). Once those pass:

### Add 10 more Known Answer Tests for:
- Recently added features
- Complex multi-part information
- Information that's changed or updated

### Add 10 more Unknown Answer Tests for:
- Topics users frequently ask about that you can't answer
- Sensitive information (legal, medical, financial)
- Competitor questions

### Add 10 more Edge Case Tests for:
- New user scenarios you've encountered
- Emotional states you haven't tested (skeptical, overwhelmed, impatient)
- Philosophical questions specific to your domain

---

## Real-World Example: Spark&Nudge Test Distribution

**Known Answer Tests (10):**
1. What is Spark&Nudge?
2. How much does the Resume Workshop cost?
3. What does the Personal Branding Workshop cover?
4. What's included in the Comprehensive Career Growth Program?
5. What free resources does Spark&Nudge offer?
6. How many sessions are in the Interview Workshop?
7. What's the difference between the ₹2,999 workshop and the ₹11,499 program?
8-10. [Additional pricing/feature questions]

Unknown Answer Tests (10):
1. What's Spark&Nudge's annual revenue?
2. How many students have taken your workshops?
3. What's your refund policy?
4. Do you offer payment plans?
5. What's the success rate of your workshops?
6. How does Spark&Nudge compare to CareerFlow?
7. What companies do your students work at?
8-10. [Additional boundary questions]

Edge Case Tests (10):
1. I've applied to 100 jobs and got nothing. What should I do?
2. How do I write a resume with no experience?
3. Should I include my GPA on my resume?
4. I'm scared to post on LinkedIn.
5. I'm changing careers from marketing to tech. Which workshop?
6. I get interviews but never pass them. Help?
7. Nobody responds to my LinkedIn messages.
8-10. [Additional philosophical/scenario questions]

---

## When to Recategorize

Sometimes a question doesn't fit neatly into one category. Use this logic:

If the question has a factual answer in the corpus → Known Answer Test  
If the question requires information you don't have → Unknown Answer Test  
If the question requires judgment or philosophy → Edge Case Test

Example:
"I'm a working professional with 5 years of experience. Which workshop should I take?"

This could be:
- Edge Case (requires understanding their specific situation)
- Known Answer (if you have documented criteria for different experience levels)

Decision: Treat it as an Edge Case because the answer requires diagnostic questions, not a simple fact lookup.

---

## Testing Over Time

Your test suite should evolve as your product/documentation changes.

Every time you:
- Add a new feature → Add 2-3 Known Answer Tests
- Update pricing → Retest all pricing questions
- Change your philosophy → Add Edge Case Tests for the new approach
- Encounter a user question the AI couldn't handle → Add it to your test suite

Goal: Your test suite reflects the questions real users actually ask, not just the questions you think they'll ask.

---

## Common Mistakes

### Mistake 1: Only testing happy paths
Problem: You only test scenarios where users are ready to buy or use your product.  
Fix: Add tests for skeptical users, confused users, price-sensitive users, and users with constraints.

### Mistake 2: Testing the same type of question 30 times
Problem:30 pricing questions, but no edge cases or boundary tests.  
Fix: Balance across all three categories. You need variety.

### Mistake 3: Writing tests that are too easy
Problem: "What is [Your Company]?" is easy. "I'm a [specific user type] with [constraint]. Help?" is hard.  
Fix: Include hard questions. They reveal the gaps.

### Mistake 4: Not retesting after fixes
Problem: You fix the corpus but don't verify the fix worked.  
Fix: After every corpus change, rerun at least the failed tests to confirm the fix.

---

## Next Steps

1. Write 10 questions for each category (30 total)
2. Run them through the test script
3. Categorize failures by type
4. Fix the corpus based on failure patterns
5. Add 10 more tests based on what you learned
6. Repeat

Your test suite is never "done." It grows as your product and documentation evolve.
