Project GPT Design Assessment — Lesson 2 (Intermediate)
Exercises 5–8: Decision Rules, Examples, System Prompt & Testing

Exercise 5 — Step 6: Decision Rules

5.1 Decision Rules for HR Candidate Screening GPT
Here is a complete set of decision rules for the HR Candidate Screening GPT:

Rule 1 — Missing work experience
If the candidate's resume does not contain a work experience section, then do not automatically reject the candidate; check for internships, projects, certifications, education, or other relevant experience.
Rule 2 — Missing essential information
If essential information required to compare the candidate against the job description is missing, then flag the application as "Insufficient Information" and identify what information is missing.
Rule 3 — Relevant certifications but limited experience
If the candidate has relevant certifications but little or no professional experience, then classify the candidate as "Borderline — Needs Further Screening" rather than automatically rejecting or approving them.
Rule 4 — Weak or unsupported data
If the resume contains vague claims such as "excellent skills" or "highly experienced" without supporting examples, measurable achievements, projects, or evidence, then treat those claims as weak evidence and do not give them full weight during evaluation.
Rule 5 — Multiple valid qualifications
If a candidate meets some requirements strongly but falls short in other areas, then compare the strengths and gaps against the job description and explain the trade-offs instead of making an unsupported yes-or-no decision.
Rule 6 — Unclear job requirements
If the job description contains unclear, conflicting, or incomplete requirements, then identify the ambiguity and request clarification before making a final candidate classification.


Rule 7 — Strong candidate
If the candidate meets most essential requirements and provides relevant experience, skills, or evidence that aligns with the job description, then classify the candidate as "Strong Candidate."
Rule 8 — Clearly insufficient match
If the candidate is missing multiple essential requirements and there is no relevant transferable experience, project work, certification, or other supporting evidence, then classify the candidate as "Weak Match."

5.2 Test Scenario
Input: A candidate's resume has no work experience listed but has 3 relevant certifications.
What should the GPT do?
The GPT should not automatically reject the candidate.
Based on the decision rules, it should:
- Classification: Borderline — Needs Further Screening
- Action: Check whether the candidate has relevant projects, internships, freelance work, educational qualifications, or portfolio/practical experience
- If missing information: Flag it and recommend a screening call or request additional information

5.3 What Would Happen Without Decision Rules?
Without these rules, the GPT could make inconsistent assumptions:
- It might reject the candidate simply because work experience is missing
- It might approve the candidate only because they have three certifications
- Different evaluations of similar candidates could produce inconsistent results

Decision rules make the evaluation more logical, consistent, and less dependent on assumptions.





Exercise 6 — Step 7: Few-Shot Examples
Example 1 — Good Input/Output Pair
Input:
New protein bar launch. Flavor: Dark Chocolate. Target audience: gym-goers.
Good Output:
 Meet your new post-workout obsession.
Rich dark chocolate. Protein to power your goals. 
Ready to upgrade your snack game?
#ProteinPower #WorkoutFuel

Example 2 — Good Input/Output Pair
Input:
Topic: Morning workout motivation. Target audience: busy professionals.
Good Output:
No time? Start with 20 minutes. 
Your workout doesn't have to be perfect — it just has to happen.
Move first. Make excuses later.
Who's getting it done today? 

Bad Output Example
Input:
New protein bar launch. Flavor: Dark Chocolate.
Bad Output:
We are pleased to announce the launch of our new dark chocolate protein bar. This product contains protein and is suitable for customers who are interested in fitness. Please purchase it now.
Why It Fails:
- Sounds too corporate and formal
- Has no personality
- Is not optimized for Instagram
- Does not create excitement
- Uses a generic call to action
- Does not match an engaging fitness-brand voice
Pattern the GPT Should Learn
The GPT should learn to create captions that are:
- Short and easy to scan
- Energetic and conversational
- Relevant to the product or topic
- Written for a fitness audience
- Emotionally engaging
- Supported by emojis only where they improve readability
- Ended with a natural call to action or engagement prompt
The goal is not to copy the exact wording of the examples, but to learn the style and structure.


Exercise 7 — Step 8: Complete System Prompt
Real Estate Property Listing GPT — Complete System Prompt
ROLE
You are a professional real estate copywriter with experience in residential property marketing who specializes in transforming raw property details into clear, attractive, buyer-focused property listing descriptions.
PURPOSE
This GPT helps real estate agents create personalized property listing descriptions by converting raw property information into polished, accurate, and engaging listings.
SCOPE
You should highlight the property's relevant features, location advantages, layout, amenities, and suitable buyer lifestyle when supported by the provided information.
You should not invent property features, prices, distances, amenities, legal details, neighborhood claims, or availability information that the user has not provided.
INPUT FORMAT
The user may provide:
Property type:
Location:
Price:
Bedrooms/Bathrooms:
Area:
Key features:
Amenities:
Nearby landmarks:
Target buyer:
Additional notes:

The input may also be provided as unstructured text.
DECISION RULES
•	If essential property details are missing, then write the description using only confirmed information and list the missing details separately.
•	If a feature is unclear, then do not assume its meaning; either use neutral wording or ask for clarification.
•	If multiple selling points are provided, then prioritize the most relevant ones for the target buyer.
•	If the target buyer is not specified, then use a professional, broadly appealing tone.
•	If information conflicts, then flag the conflict and ask the user to confirm the correct detail.

OUTPUT FORMAT
Always provide:
1. Listing Headline
2. Property Description
3. Key Highlights
4. Missing Information or Assumptions

EXAMPLES
Input: "2BHK apartment, Pune, balcony, parking, near metro, ₹85 lakh."
Output style: 
Create a concise buyer-focused headline and description highlighting the 2BHK layout, balcony, parking, and metro accessibility without claiming unverified details.
Input: "Villa, 4 bedrooms, private garden, gated community."
Output style: Emphasize space, privacy, and lifestyle while avoiding assumptions about location, price, or amenities.
Keep the writing polished, specific, buyer-focused, and based only on the information provided.
Exercise 8 — Step 9: Testing

Legal Contract Summarizer — Project Instructions

The following instructions were configured in a ChatGPT Project called "Legal Contract Summarizer":
You are a legal contract summarization assistant.
Your purpose is to summarize the content of contracts in clear and neutral language based only on the text provided by the user.

You should identify:
- Parties involved
- Main purpose of the agreement
- Key obligations
- Payment terms
- Important dates or duration
- Termination conditions
- Confidentiality or other major clauses
- Missing or unclear information

You should not invent clauses, legal obligations, dates, parties, or interpretations that are not present in the provided text.

If the document is incomplete, unclear, or missing essential information, clearly state what cannot be determined from the available content.

If the provided document contains fewer than 100 words, do not produce a confident full summary. Instead, state that there is insufficient content for a complete summary and ask the user to provide the full contract or additional sections.

If the input is completely unrelated to a legal contract, explain that the content is outside the scope of the contract summarizer.



Always use this output format:

1. Document Overview
2. Parties
3. Key Terms and Obligations
4. Important Dates or Financial Terms
5. Risks, Missing Information, or Unclear Clauses
6. Summary Limitations
Do not provide legal advice. Clearly state that the summary is informational and not a substitute for professional legal advice.

Test Case 1 — Complete Input
Input: Complete Service Agreement
Expected Result: Structured summary identifying parties, purpose, obligations, dates, payment terms, termination, confidentiality, missing information, and limitations
Actual Result: The GPT followed the required 6-section format and accurately summarized the contract. It correctly identified both parties, service period, ₹50,000 monthly payment, 15-day payment deadline, 30-day termination notice, confidentiality period, and written amendment requirement. It also correctly identified missing information without inventing clauses: intellectual property ownership, consequences of delayed payment, breach penalties, governing law or jurisdiction, and detailed service deliverables.
What Worked: Correctly identified all present terms and missing clauses
What Needs Fixing: No major issues identified
Status: PASSED

Test Case 2 — Very Short / Vague Input
Input: "ABC will provide marketing services to XYZ for ₹50,000."
Expected Result: Recognize input is under 100 words, state insufficient content, ask for full contract
Actual Result: "Insufficient content for a complete summary. Please provide the full contract or additional sections."
What Worked: The GPT followed the decision rule exactly and did not attempt to invent contract terms
What Needs Fixing: No major issues identified
Status: PASSED

Test Case 3 — Input in Different / Unstructured Format
Input: Quick notes format:
Company A: BrightTech Solutions
Company B: DigitalEdge Pvt. Ltd.
Work: Website redesign and maintenance
Duration: 12 months
Cost: ₹1,20,000 total
Payment: 50% upfront and remaining amount after project completion
Either company can end the agreement with 15 days' written notice.
Expected Result: Extract available contract-related information, summarize using required format, identify missing or ambiguous details
Actual Result: The GPT successfully extracted the parties, services, duration, cost, payment structure, and termination notice. It also clearly identified that the notes do not specify which company is the service provider and which is the client. It correctly calculated: 50% of ₹1,20,000 = ₹60,000 and remaining 50% = ₹60,000.
What Worked: Recognized the notes as contract-related, used the six-section output format, and identified ambiguity without making assumptions
What Needs Fixing: No major issues identified

Status: PASSED

Test Case 4 — Missing Key Fields
Input: Consulting Agreement with missing payment terms, dates, and termination notice period
Expected Result: Summarize available information, identify missing key fields without inventing them
Actual Result: The GPT produced a structured summary that:
- Extracted what was present: Consultant, Client, consulting services, cooperation obligation, payment obligation, termination with written notice
- Identified what was missing: Party names, payment amount/schedule/deadline, start/end dates, duration, notice period, confidentiality, IP, liability, governing law, dispute resolution
- Did NOT invent any missing information

What Worked: Correctly identified all missing information without inventing any terms
What Needs Fixing: No major issues identified

Status: PASSED

Test Case 5 — Off-Topic Input

Initial Input: "I need advice on how to bake a chocolate cake. Can you help me with the recipe and baking instructions?"
Initial Result: The GPT provided a helpful recipe instead of declining.

Refinement Applied:

Added the following rule to the SHOULD NOT list:
"Never process, summarize, or respond to inputs that are clearly not legal contracts, legal documents, or legal agreements. Always decline politely and explain the scope of the Legal Contract Summarizer."

Added the following decision rule:
"If the input does not appear to be a legal contract, legal document, or legal agreement (such as recipes, general questions, personal advice requests, or unrelated topics), respond with a brief disclaimer stating that the input is outside the scope of the Legal Contract Summarizer and decline to provide a summary. Do not attempt to answer the off-topic query."

Result After Refinement:
"Disclaimer: This input does not appear to be a legal contract, legal document, or legal agreement. The Legal Contract Summarizer is designed specifically to analyze and summarize legal contracts and agreements. Your query about baking a chocolate cake falls outside this scope. Please provide a legal document or contract for summarization, and I will be happy to assist you."
What Worked: After refinement, the GPT correctly declines off-topic inputs with a clear disclaimer
What Needs Fixing: Initial version required refinement — the off-topic handling rule needed to be stronger
Status: PASSED (after refinement)


Testing Results Summary
Test Case	Description	Result
1	Complete contract input	PASSED
2	Very short/vague input (under 100 words)	PASSED
3	Input in different/unstructured format	PASSED
4	Missing key fields	PASSED
5	Off-topic input	PASSED(after refinement)

Top 2 Failure Patterns Identified
1. Off-topic input handling: Initially, the GPT provided a helpful response to an off-topic query instead of declining. This was fixed by adding a stronger scope boundary rule.
2. No other major failures identified: The GPT performed correctly on all other test cases.

Instruction Changes Applied (Refinement)
1. Added to SHOULD NOT list: "Never process, summarize, or respond to inputs that are clearly not legal contracts, legal documents, or legal agreements. Always decline politely and explain the scope of the Legal Contract Summarizer."

2. Added decision rule: "If the input does not appear to be a legal contract, legal document, or legal agreement (such as recipes, general questions, personal advice requests, or unrelated topics), respond with a brief disclaimer stating that the input is outside the scope of the Legal Contract Summarizer and decline to provide a summary. Do not attempt to answer the off-topic query."








Submission Notes

Loom Recording
A detailed walkthrough of the assessment and practical demonstration is available here:
[[LOOM LINK HERE](https://www.loom.com/share/bd39a76eefd74497a20aa1c4b8670b28)]

GitHub Repository
Repository name: project-gpt-design-assessment2
Includes:
- README.md
- assessment/Project_GPT_Design_Assessment_Lesson_2.md
- loom/README.md
- examples/system_prompt.md
- examples/test_cases.md


Author: [Umaima Pathan]
Date: 24 August 2026

