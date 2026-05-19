# Prompt Log — Shiva Ramdath

**Project:** Threat Intelligence Feed
**Team:** [Team name]
**My Component:** Relevance Scorer
**AI Tools Used:** GitHub Copilot, Gemini

---

## 2026-05-16 — generating test data for testing

**Context:** 
Files opened: Gemini, Project Airtable, Project n8n workflow

**Prompt:**
> Generate 5 articles, around 500 words each for a threat intelligence feed with a scope in phishing detection.
> 1 article that contains spam or irrelevant content such as ADs, html tags, navigation links, etc.
> 1 article that discusses basic online threats
> 1 article that discusses phishing email threats
> 1 article that contains spam but contains vague content of online threats
> 1 article that discusses about online threats linked to spam

**Result:** 
Gemini produced 3 distinct text samples. It stated the article type and the article's use case.

**Evaluation:** 
The text samples were accurate and helpful in testing my component. It provided an error case, a normal case, a scope specific case and 2 edge cases.

**What I changed:** 
Adjustments were made to my components nodes such as my Groq prompt. These adjustments were made to identify edge cases such as article 4 & 5. Through adjusting my prompt, I was able to identify some edge cases but inevitably I had to route majority of these edge cases for human review.

**What I learned:** 
Next time, I would prompt the AI to generate shorter text. One of the issues I ran into whilst analyzing the text sample was that it was too lengthy and so I had to utilize a snippet of it instead. Limiting the text samples to 100-200 words would be sufficient for further testing.

---

## 2026-05-19 — generating more test data for individual component testing

**Context:** 
Files opened: Gemini, Relevance Scorer Airtable, Relevance Scorer n8n workflow

**Prompt:**
> Summarize the 5 genereated articles in 3-4 bullet points. Each bullet point should include:
> 1 bullet point dedicated to pulling the relevant tech stack from the threat article
> 1 bullet point about the affected software from the threat article
> 1-2 bullet points providing clear descriptions about the threat article

**Result:** 
Gemini produced 4 bullet points per article that produced the Tech Stack, Affected Software, Core Content and Further Context. 

**Evaluation:** 
The bullet point lists were useful for testing my individual component. Gemini served as the AI Summarizer/IOC Extractor and its output was utilized to develop the relevance score, severity, matched tech stack and reasoning.

**What I changed:** 
I realized that my component should be built to enrich the AI summary and not the actual threat article. Hence, I adjusted my input text and my Groq prompt once again. These adjustments were made to properly classify the bullet point lists and generate the proper data.

**What I learned:** 
I learnt how simple my component really is that I had anticipated it to be. I had also learnt how to take a generated tech stack and match it with a built-in tech stack list. This is a useful skill, as the built-in tech stack can highlight specific technologies, allowing users to address issues more effectively and respond to time-sensitive threats more quickly
