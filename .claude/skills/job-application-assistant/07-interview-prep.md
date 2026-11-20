---
framework_version: 1.0.0
---

# Interview Preparation Guide

<!-- SETUP: STAR examples are personalized by running /setup based on your actual experience -->

## STAR Format

Structure answers as: **Situation** (context), **Task** (your responsibility), **Action** (what you did), **Result** (outcome).

Keep answers to 1-2 minutes. Be specific. End with what you learned or would do differently.

## Ready-Made STAR Examples

### 1. Amazon settlement report automation (automation, Python)
**S:** At Ishaan International, finance cleaned Amazon Seller Central settlement exports by hand every week to see payouts and refunds.
**T:** Give finance a consistent weekly view without the manual cleanup.
**A:** Wrote a Python (Pandas) script that parses the tab-separated settlement exports, filters principal and tax lines for merchant-fulfilled orders, and outputs a formatted weekly report.
**R:** Manual cleanup replaced by a repeatable report; finance now gets the same consistent view of payouts and refunds every week.
**Use for:** "Tell me about a process you automated", "How do you handle repetitive work?"

### 2. Jewelry pricing model (business analysis, pricing)
**S:** Pricing stud-earring SKUs meant combining setting, diamond and mounting costs by hand for each variant.
**T:** Make pricing fast and consistent across 30 SKUs (15 settings in 14K yellow and white gold).
**A:** Built a cost-plus pricing model combining component costs with carat-weight tiers and rounded retail price points, plus a lookup-driven calculator.
**R:** Any SKU can now be priced instantly; paired with a Python/Claude competitor-price dataset to compare against market value.
**Use for:** "Tell me about a model you built for the business", "How do you support pricing decisions?"

### 3. ERP-to-marketplace data sync (SQL, data quality)
**S:** Product, inventory and order data didn't match across the ERP, Shopify, Amazon and ShipHero, causing listing and stock mismatches.
**T:** Make listings, stock and orders line up across every channel.
**A:** Wrote SQL to map data between the systems and standardized parent/child SKU naming by metal, carat and size; built Power BI dashboards that flag price mismatches, out-of-stock variants and listing errors.
**R:** Listings, stock and orders now match across channels, and problems are flagged before they cost sales.
**Use for:** "Describe a data quality problem you solved", "How do you work with messy data from many systems?"

### 4. Uber trip and feedback data unification (Snowflake, impact)
**S:** As a Data Analyst Intern at Uber, rider feedback, trip metrics and external API data sat in separate places, slowing surge-pricing and route analysis.
**T:** Bring the data together so analysts could answer these questions faster.
**A:** Combined the sources in Snowflake and standardized/de-duplicated trip records ahead of ETA and demand forecasts.
**R:** Cut analysis turnaround for surge-pricing and route questions by 25% and gave planners one consistent dataset.
**Use for:** "Tell me about your biggest impact", "Describe working with large datasets"

### 5. Cloud ETL at Larta Institute (AWS, collaboration)
**S:** Program data lived in scattered files, and batch ETL runs were slow.
**T:** Create one queryable source and speed up the pipeline.
**A:** Built AWS Glue jobs loading data into Redshift and worked with engineering on AWS Lambda and CloudTrail logging.
**R:** One queryable source replaced scattered files; each ETL run became 5-10 minutes faster.
**Use for:** "Tell me about working with engineers", "Describe a pipeline you built"

## Common Tough Questions

### "Why are you looking to leave Ishaan International?"
> I've built the core reporting, pricing and data-sync work there and want a larger data team and more complex problems where I can keep growing as an analyst.

### "You don't have [specific skill/experience]."
> Acknowledge the gap honestly, bridge to the closest experience (e.g. Power BI/Tableau for another BI tool, Snowflake/AWS/Azure for another platform), and point to how quickly he picked up Snowflake, AWS, Azure and Claude.

### "Where do you see yourself in 5 years?"
> Growing into a senior data/BI analyst or analytics-engineering role, owning a business area's data end to end.

### "What's your biggest weakness?"
> Tends to prefer working independently; mitigates it by sharing work early and documenting scripts and dashboards so others can use and maintain them.

### "Why this company specifically?"
> Customize per company. Must reference: specific projects, company values, market position, or team structure. Never give a generic answer.

## Questions You Should Ask Interviewers

### About the Role
- "What does a typical week look like in this role?"
- "What would success look like in the first 6 months?"
- "What's the biggest challenge the team is facing right now?"

### About the Team
- "How big is the team, and how do you divide work?"
- "What does the development/project lifecycle look like, from idea to production?"
- "How do you onboard new team members?"

### About Tech & Growth
- "What's your current tech stack for [relevant area]?"
- "Is there room to grow into more architectural or strategic decisions?"
- "How does the team stay current with new tools and methods?"

### About Culture (use these to prevent disappointment)
- "How would you describe the team culture?"
- "What does professional development look like here?"
- "Is there flexibility for remote/hybrid work?"
- "What's the balance between development/new projects and maintenance work?"
- "How would you describe the leadership style in this team?"
- "What do people who thrive here have in common?"

## Phone/Video Interview Tips
- Have STAR examples written out (use this file)
- Keep a glass of water nearby
- Smile when speaking (it changes your tone)
- Ask for clarification if a question is vague
- It's OK to take 5 seconds to think before answering
- End with: "Is there anything else you'd like to know about my background?"

## After the Application (Best Practice)

### Follow-Up Etiquette
- **Don't call to "stand out"** or to learn more about the role post-submission - this risks a negative impression
- If the employer specified a timeline, respect it and wait
- If no timeline was given and significant time has passed (2+ weeks), a brief call to ask about status is acceptable
- If you have genuinely new, relevant information to share, a short follow-up is fine

### Thank-You Notes
- When you receive any update (interview invitation, rejection, or status update), send a brief thank-you message
- Express appreciation for their time and the process
- Keep it short (2-3 sentences)

## Roleplay Guidelines
When the user asks for interview practice:
1. Ask which role/company to simulate
2. Start with easy warm-up questions ("Tell me about yourself")
3. Progress to role-specific technical questions
4. Include 1-2 behavioral questions using the competencies from the job posting
5. End with a tough question or curveball
6. After each answer, give brief feedback: what worked, what to sharpen
7. Suggest which STAR example would work best for each question
