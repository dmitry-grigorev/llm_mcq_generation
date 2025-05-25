# LLM Multiple choice questions generation
Project with the utilization of LLM chosen for MCQ generation based on provided input (books, articles)

As model used for generation [**Qwen2.5-1.5B-instruct**](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct)  is used thanks to its availability, efficiency.

The questions generated are supposed to follow Bloom's taxonomy, 3 first types of questions are chosen -- Remember, Comprehension and Application -- as the types of higher order in the taxonomy are harder to represent in MCQ. Indicator-words that are typical for each level of taxonomy are referenced from [the link](https://www.swtxc.edu/documents/oipr/bloom.pdf)

Additionaly, the generation was assessed by Gemma-3 ([Gemma-3-4b-it](https://huggingface.co/google/gemma-3-4b-it)) judge in terms of compliance with generation prompt.

As example, for one book the intermediate results of the whole process of generation are presented:
- Book scanning for key words (terms) and all contexts where the words appear
- Selection of best-fitting contexts for each term (by means of the LLM) in terms of the context containing description/functions of the term and tournmanet-like preselection in case when the number of contexts collected is large.
- The resulted MCQ collection generated on the selected term-context pairs.

Interface for MCQ is made by means of [gradio](https://www.gradio.app/docs/python-client/introduction) .
