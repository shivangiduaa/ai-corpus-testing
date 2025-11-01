How to Structure Your Corpus
Your corpus is the foundation of your AI's knowledge. Structure it well, and your AI will give accurate, on-brand responses. Structure it poorly, and it will hallucinate.

The 8 Core Sections
1. Brand Voice & Philosophy
What it is: Examples of how your brand communicates, with explicit good vs. bad examples.
Why it matters: The AI learns your tone, values, and communication style from examples, not descriptions.
What to include:

3-5 examples of responses in your brand voice
3-5 examples of what NOT to say (generic, corporate, off-brand)
Your core philosophy statements
2. Factual Information
What it is: Concrete, verifiable information about your product/service.
Why it matters: This is where most hallucinations happen. If pricing, features, or policies aren't explicit, the AI will guess.
What to include:

Pricing (exact numbers, currency)
Product/service names (exact spelling, capitalization)
Features and what they include
Technical specifications
Availability, timelines, deadlines

3. Conversation Patterns
What it is: Examples of HOW to structure responses, not just what to say.
Why it matters: The AI learns response flow from patterns. Show it how to open, develop, and close responses.
What to include:

How to start responses (empathetic acknowledgment? Direct answer? Question?)
How to structure multi-part answers
How to transition between topics
When to ask follow-up questions

4. Explicit Boundaries
What it is: What the AI should say when it doesn't have information.
Why it matters: This prevents hallucinations. If the AI doesn't know, it should say so, not make something up.
What to include:

Standard "I don't know" phrasing
What information the AI should NOT have
When to redirect to human contact


5. Edge Case Responses
What it is: How to handle ambiguous, emotional, or philosophical questions.
Why it matters: These questions don't have factual answers. The AI needs to match your brand's approach.
What to include:

Responses to frustrated users
Responses to vague questions
How to handle unrealistic expectations
When to be empathetic vs. direct

6. Specific Scenarios
What it is: Common user situations and how to handle them.
Why it matters: Real users have specific contexts. The AI needs to adapt advice to their situation.
What to include:

Career changers
Different experience levels (students, mid-career, senior)
Geographic or industry-specific considerations
Users with constraints (time, budget, resources)

7. How to End Conversations
What it is: Natural conversation closings and calls to action.
Why it matters: The AI needs to know when to wrap up, what CTAs to offer, and how to leave the door open.
What to include:

When to suggest booking a call
When to recommend a specific resource
How to end without being abrupt
What CTAs are appropriate when

8. Final Reminders & Red Flags
What it is: Things the AI should ALWAYS remember and things it should NEVER do.
Why it matters: These are your guardrails. They prevent the AI from drifting off-brand even when it thinks it's being helpful.
What to include:

Core principles to never violate
Red flag phrases to avoid
Reminders about tone and approach
What NOT to promise or guarantee

Corpus Size Guidelines
Minimum viable corpus: 15-20 pages (5,000-6,000 tokens)
Recommended for production: 40-50 pages (15,000-20,000 tokens)
Why? Statistical language models need enough data to learn reliable patterns. Under 5,000 tokens, the AI won't have enough examples to generalize.

Testing Your Corpus Structure
Before running AI tests, do a manual check:
✓ Does each section have 3+ examples? One example isn't enough for the AI to learn a pattern.
✓ Are factual statements unambiguous? No "around," "approximately," "typically." Use exact numbers and terms.
✓ Do you show conversation flow, not just facts? The AI needs to see HOW to respond, not just WHAT to say.
✓ Have you included "I don't know" boundaries? If you don't explicitly tell the AI what it shouldn't answer, it will try to answer everything.
✓ Is your brand voice consistent? Read through the whole corpus. Does it sound like one person talking, or 10 different blog posts stitched together?

Common Mistakes
Mistake 1: Describing voice instead of showing it
Wrong: "Be friendly and professional."
Right: [5 examples of friendly, professional responses in action]
Mistake 2: Vague factual information
Wrong: "Our workshops are affordable and include multiple sessions."
Right: "The Resume Workshop costs ₹1,999 INR and includes 3 live sessions."
Mistake 3: No boundaries
Wrong: [No section about what the AI shouldn't answer]
Result: AI makes up answers to questions it doesn't have information for.
Mistake 4: Only including happy path scenarios
Wrong: [Only examples of users who are ready to buy]
Right: [Examples of frustrated users, skeptical users, confused users, price-sensitive users]

Next Steps

Write your corpus using this 8-section structure
Calculate lexical diversity (use online tools or Python's NLTK library)
Run word frequency analysis to see what words dominate
Test with the provided test script
Iterate based on failures

Your corpus will never be "done." It's a living document that evolves as you find new failure patterns and user scenarios.
