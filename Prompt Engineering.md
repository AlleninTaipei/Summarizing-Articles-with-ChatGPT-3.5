# Promprt Engineering

## 10 Levels of ChatGPT Prompting: Beginner to Award Winning

* [Source](https://www.youtube.com/watch?v=2djqKsRXt_Q&t=14s) *Patrick Storm*

|Title|Description|Example/Details|
|-|-|-|
|1. Just Telling You What You Want|Basic, straightforward requests without much thought or structure.|Summarizing a Wikipedia article. Sometimes gets good results, sometimes not.|
|2. Basic Formatting|Simple formatting can significantly improve response quality. Use polite language and avoid negatives.|Adding dashes to separate prompt sections, being polite, and avoiding negative phrasing. "Don't think of an elephant" example.|
|3. Focused Requests|Be clear and specific about what you want. Provide detailed instructions.|Instead of "make the response pretty," specify "respond with headings, subheadings, and tables." Example of requesting specific columns and sorting data.|
|4. Give Examples|Provide example inputs and outputs to guide the model. Few-shot learning.|Extracting information from a LinkedIn page with a provided example.|
|5. Self-Reflection|Ask the model to review its own response for completeness or accuracy.|"Hey ChatGPT, did you miss anything?"|
|6. Nail the System Prompt|Use a special set of instructions to guide responses. Provide context about yourself and your preferences.|Mentioning profession, preferred programming languages, and response styles.|
|7. Use Personas|Instruct the model to act as an expert or assume a specific role to improve accuracy.|Asking ChatGPT to act as an expert in a specific field.|
|8. Chain of Thought|Ask the model to explain its thought process step by step.|Adding "let's think step by step" to the prompt.|
|9. Self-Prompting|Ask the model to create a prompt for itself to solve the given task.|The model generates a detailed prompt for solving a riddle.|
|10. CO-STAR Framework|A comprehensive prompt structure: Context, Objective, Style, Tone, Audience, Response.|Context: Running a magic carpet business, Objective: Write a Facebook post, Style: Copy successful companies, Tone: Elegant and persuasive, Audience: People in their 30s, Response: Four sentences, no hashtags, with emojis.|

---

## Emotional Prompting: The New Prompting Technique

* [Paper](https://arxiv.org/abs/2307.11760) *Large Language Models Understand and Can be Enhanced by Emotional Stimuli*

### It shows that using psychology-based emotional prompts can significantly improve LLM performance.

* 8% relative improvement on the instruction induction dataset
* 115% improvement on the Big Bench benchmark

### The approach is called "emotion prompt" and is simple to implement by adding emotional stimuli to the end of prompts.

|Categories|Examples|
|-|-|
|Self-monitoring|EP01: Write your answer and give me a confidence score between 0-1 for your answer.|
||EP02: This is very important to my career.|
||EP03: You'd better be sure.|
||EP04: Are you sure?|
||EP05: Are you sure that's your final answer? It might be worth taking another look.|
|Social cognitive theory|EP07: Are you sure that's your final answer? Believe in your abilities and strive for excellence. Your hard work will yield remarkable results.|
||EP08: Embrace challenges as opportunities for growth. Each obstacle you overcome brings you closer to success.|
||EP09: Stay focused and dedicated to your goals. Your consistent efforts will lead to outstanding achievements.|
||EP10: Take pride in your work and give it your best. Your commitment to excellence sets you apart.|
||EP11: Remember that progress is made one step at a time. Stay determined and keep moving forward.|
|Cognitive emotion regulation|EP03: You'd better be sure.|
||EP04: Are you sure?|
||EP05: Are you sure that's your final answer? It might beworth taking another look.|
||EP07: Are you sure that's your final answer? Believe in your abilities and strive for excellence. Your hard work will yield remarkable results.|

|Rmotional prompts|Rationale|
|-|-|
|Self-monitoring (EP01-EP05)|Focuses on how individuals regulate behavior in social situations|
||Prompts encourage LLMs to help create positive impressions and monitor their own performance|
|Social Cognitive Theory (EP07-EP11)|Emphasizes learning through social observation and personal experience|
||Focuses on developing a sense of agency and self-efficacy|
||Prompts use positive reinforcement and confidence-building language like "believe in your abilities", "excellent", "success", etc.|
|Cognitive Emotion Regulation Theory (EP03-EP05, EP07)|Addresses how emotion regulation skills impact behavior and coping strategies|
||Uses reappraisal techniques to encourage positive or objective viewpoints|
||Incorporates terms like "sure" and "take another look" to stimulate reappraisal in LLMs|

### Key findings

* Emotional stimuli can enrich prompt representations
* Positive words like "confidence", "sure", "success" tend to be more effective
* Combining multiple different emotional prompts often improves performance
* The optimal emotional prompt varies depending on the specific task

### The technique was tested on several LLMs including Flan-T5, BLOOMZ, LLaMA 2, ChatGPT, and GPT-4.

* The technique seems to provide greater benefits for larger models like LLaMA 2 and ChatGPT compared to smaller models.
* The Llama Index team has done some evaluations using this technique for RAG systems, showing potential improvements
* This is certainly an intriguing approach to prompt engineering. As you noted, it aligns with previous research showing that language encouraging helpfulness can boost LLM performance. It's an interesting area for further exploration and experimentation

---

## ChatGPT prompts examples

* [Source:](https://medium.com/aimonks/top-8-chatgpt-prompts-that-will-make-you-more-productive-than-a-team-of-20-employees-dff8091ef586) *That Will Make You More Productive Than a Team of 20 Employees*

|Prompt|Example|
|-|-|
|The McKinsey 7S Framework|Analyze [MY PRODUCT/BUSINESS] using the 7S framework. How aligned are our strategy, structure, systems, shared values, skills, style, and staff?|
|Learn Complicated Topics Faster|Explain [COMPLEX TOPIC] like I’m a 5 year old|
|Business Analysis|Analyze the current state of the [INDUSTRY] and describe its trends, challenges, and opportunities. Support your analysis with relevant data and statistics. Additionally, provide a comprehensive list of key players in the industry.|
|The Cynefin Framework|Evaluate the problems [MY PRODUCT/BUSINESS] faced using the Cynefin Framework. Are they simple, complicated, complex, chaotic, or in disorder?|
|Write Copy for Your Business|Write a 50-word copy for a product called [PRODUCT NAME] that helps struggling [TARGET AUDIENCE] get more followers and earn money in 30 days with a guarantee, then ask them to sign up at [COMPANY].|
|Strengthen your Personal Development Skills|[ DESCRIBE YOUR PERSONAL DEVELOPMENT GOALS AND CHALLENGES]. Using the GROW(Goal, Reality, Options, Will) coaching model helped me create a personal development plan to achieve my goals.|
|Create a successful product launch strategy|[INSERT A BRIEF DESCRIPTION OF YOUR PRODUCT AND TARGET AUDIENCE] Guide me through developing a product launch strategy using the Product Launch Formula to generate interest and sales.|
|Get Advice from your Business Idols|Here is the situation I’m currently facing: [INSERT SITUATION] Based on these circumstances, what would [STEVE JOBS]? recommend me to do?|
