# Is GPT-2 good at maths?

This is an exploration of GPT-2's performance on mathematical reasoning tasks. Despite the proven capabilities of Large Language Models (LLMs) across various applications multi-step mathematical reasoning still exposes significant limitations in these models.

Our study uses the GSM8K dataset, made by elementary level math problems, to assess how well GPT-2 can handle such tasks. We focus on optimizing hyperparameters like beam size and temperature to enhance the model’s problem-solving accuracy, diving deep into how these settings influence GPT-2's performance on mathematical challenges.

# About the model

We used the GPT-2 model provided by OpenAI. More information about this model can be retrieved at https://huggingface.co/openai-community/gpt2. We selected this model for many reasons: it is relatively small; it has already been trained on big amount of data; the model and the corresponding weights have been made publicly available online. 

## Evaluation

HuggingFace provides the [Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard), which ranks LLM models, including GPT-2, on different tasks, including the GSM8k. The leaderboard uses the [Model Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness) utility built by EleutherAI to evaluate the models.

## Methodology

We used 20 combinations of 5 different temperature and 4 beam settings to test the performance of the GPT-2 model on the GSM8K benchmark.
The temperature settings ranged from 0 to 1 (0, 0.1, 0.5, 0.7, 1). Lower temperature values lead to less diverse responses, while higher values lead to more diverse responses. The reasoning behind these values is to hopefully get a balance between quality and diversity of the responses provided by the model. 
The beam size settings ranged from 1 to 6 (1, 2, 3, 6). Although it was possible to use a higher number of beams, we opted to stop at six, due to the constraints of our computational resources, which made larger beam sizes impractical. Usually, smaller beam sizes are more suitable for solving mathematical problems, where deterministic answers are desirable, in contrast to text generation tasks where greater creativity and diversity may benefit from larger beam sizes. After conducting all the experiments, the results were combined into a singular matrix to see if there were any patterns.
To make sure that the optimal value is not due to random sampling, we repeatedly executed the same model with beam size 3 and temperature 0.7.

## Authors

P. Sabournia: [@PejmanSa](https://github.com/PejmanSa)

P.A. van Beek: [@PablovanBeek](https://github.com/PablovanBeek)

K. Kunst: [@Kamielk01](https://github.com/Kamielk01)

G. Migliore: [@GiuliMigliore](https://github.com/GiuliMigliore)