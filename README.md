## Introcuction

Large language models (LLMs) have mastered abundant simple and explicit commonsense knowledge through pre-training, enabling them to achieve human-like performance in simple commonsense reasoning. Nevertheless, LLMs struggle to reason with complex and implicit commonsense knowledge that is derived from simple ones (such as understanding the long-term effects of certain events), an aspect humans tend to focus on more. Existing works focus on complex tasks like math and code, while complex commonsense reasoning remains underexplored due to its uncertainty and lack of structure. To fill this gap and align with real-world concerns, we propose a benchmark Com2 focusing on complex commonsense reasoning. We first incorporate causal event graphs to serve as structured complex commonsense. Then we adopt causal theory (e.g., intervention) to modify the causal event graphs and obtain different scenarios that meet human concerns. Finally, an LLM is employed to synthesize examples with slow thinking, which is guided by the logical relationships in the modified causal graphs. Furthermore, we use detective stories to construct a more challenging subset. 



[[Paper]](https://arxiv.org/abs/2506.07064) Com²: A Causal-Guided Benchmark for Exploring Complex Commonsense Reasoning in Large Language Models



## Benchmark

1. Benckmark

```yaml
path: benchmark/com2
com2-main: benchmark/com2/main.json
com2-hard: benchmark/com2/hard.json
```



* The structure of com2-main

```json
{
  "question": "the question to ask for outcomes.",
  "options": "containing answer(s) and distractors.",
  "think_process": "the slow thinking process guided by the causal graphs.",
  "answer": "the answer(s) to the question.",
  "chains": "two chains in the causal graphs, note that Direct task will use the first causal chain to create the example.",
  "scenario": "scenarios created for each causal chain, which is not used for data synthesis.",
  "type": "the task type of the example, such as decision and intervention.",
  "model": "the model used for example construction."
}
```



* The structure of com2-hard

```json
{
  "story_code": "the story id in BMDS stories.",
  "clue": "the key clue of the detective story, which is annotated in BMDS.",
  "criminal": "the criminal(s) of the crime",
  "crime": "the description of the crime",
  "facts": "the facts in the crime",
  "question": "the question based on the crime.",
  "options": "the options of the question",
  "investigation": "the thinking process to answer the question.",
  "answer": "the answer to the question",
  "type": "the task type of the question",
  "model": "the model used for example construction."
}
```



2. Optional training data for analysis

The training set has the same structure of com2-main.

```json
{
  "question": "the question to ask for outcomes.",
  "options": "containing answer(s) and distractors.",
  "think_process": "the slow thinking process guided by the causal graphs.",
  "answer": "the answer(s) to the question.",
  "chains": "two chains in the causal graphs, note that Direct task will use the first causal chain to create the example.",
  "scenario": "scenarios created for each causal chain, which is not used for data synthesis.",
  "type": "the task type of the example, such as decision and intervention.",
  "model": "the model used for example construction."
}
```



## Citation

```
@article{xiong20252,
  title={Com $\^{} 2$: A Causal-Guided Benchmark for Exploring Complex Commonsense Reasoning in Large Language Models},
  author={Xiong, Kai and Ding, Xiao and Cao, Yixin and Yan, Yuxiong and Du, Li and Zhang, Yufei and Gao, Jinglong and Liu, Jiaqian and Qin, Bing and Liu, Ting},
  journal={arXiv preprint arXiv:2506.07064},
  year={2025}
}
```

