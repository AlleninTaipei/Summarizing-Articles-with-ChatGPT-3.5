# Promprt Engineering

## Emotional Prompting: The New Prompting Technique

* [Paper](https://arxiv.org/abs/2307.11760) *Large Language Models Understand and Can be Enhanced by Emotional Stimuli*

### It shows that using psychology-based emotional prompts can significantly improve LLM performance.

* 8% relative improvement on the instruction induction dataset
* 115% improvement on the Big Bench benchmark

### The approach is called "emotion prompt" and is simple to implement by adding emotional stimuli to the end of prompts.

|Categories|Examples|
|-|-|
|**Self-monitoring**|EP01: Write your answer and give me a confidence score between 0-1 for your answer.|
||EP02: This is very important to my career.|
||EP03: You'd better be sure.|
||EP04: Are you sure?|
||EP05: Are you sure that's your final answer? It might be worth taking another look.|
|**Social cognitive theory**|EP07: Are you sure that's your final answer? Believe in your abilities and strive for excellence. Your hard work will yield remarkable results.|
||EP08: Embrace challenges as opportunities for growth. Each obstacle you overcome brings you closer to success.|
||EP09: Stay focused and dedicated to your goals. Your consistent efforts will lead to outstanding achievements.|
||EP10: Take pride in your work and give it your best. Your commitment to excellence sets you apart.|
||EP11: Remember that progress is made one step at a time. Stay determined and keep moving forward.|
|**Cognitive emotion regulation**|EP03: You'd better be sure.|
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
