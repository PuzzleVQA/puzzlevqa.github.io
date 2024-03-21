<div style="text-align: center;">
    <a href="https://arxiv.org/abs/2403.13315" class="button" style="margin: 10px;">Paper</a>
    <a href="https://github.com/declare-lab/LLM-PuzzleTest" class="button" style="margin: 10px;">Code</a>
    <a href="https://github.com/declare-lab/LLM-PuzzleTest" class="button" style="margin: 10px;">Dataset</a>
</div>

### About

Large multimodal models extend the impressive capabilities of large language models by integrating multimodal
understanding abilities. However, it is not clear how they can emulate the general intelligence and reasoning ability of
humans. As recognizing patterns and abstracting concepts are key to general intelligence, we introduce PuzzleVQA, a
collection of puzzles based on abstract patterns. With this dataset, we evaluate large multimodal models with abstract
patterns based on fundamental concepts, including colors, numbers, sizes, and shapes. Through our experiments on
state-of-the-art large multimodal models, we find that they are not able to generalize well to simple abstract patterns.
Notably, even GPT-4V cannot solve more than half of the puzzles. To diagnose the reasoning challenges in large
multimodal models, we progressively guide the models with our ground truth reasoning explanations for visual perception,
inductive reasoning, and deductive reasoning. Our systematic analysis finds that the main bottlenecks of GPT-4V are
weaker visual perception and inductive reasoning abilities. Through this work, we hope to shed light on the limitations
of large multimodal models and how they can better emulate human cognitive processes in the future.

### Example Puzzle

The figure below shows an example question which involves the color concept in PuzzleVQA, and an incorrect answer from
GPT-4V. There are generally three stages that can be observed in the solving process: visual perception (blue),
inductive reasoning (green), and deductive reasoning (red). Here, the visual perception was incomplete, causing a
mistake during deductive reasoning.

<img src="/images/example.png" alt="" width="972" height="1500">

### Puzzle Components

The figure below shows an illustration example of components (top) and reasoning explanations (bottom) for abstract
puzzles in PuzzleVQA. To construct each puzzle instance, we first define the layout and pattern of a multimodal
template, and populate the
template with suitable objects that demonstrate the underlying pattern. For interpretability, we also construct ground
truth reasoning explanations to interpret the puzzle and explain the general solution stages.

![](/images/components.png)

### Puzzle Taxonomy

The figure below shows the taxonomy of abstract puzzles in PuzzleVQA with sample questions, based on fundamental
concepts
such as colors and size. To enhance diversity, we design both single-concept and dual-concept puzzles.

![](/images/taxonomy.png)

### Evaluation Results

We report the main evaluation results on single-concept and dual-concept puzzles in Table 1 and Table 2 respectively.
The evaluation results for single-concept puzzles, as shown in Table 1 reveal notable differences in performance among
the open-source and closed-source models. GPT-4V stands out with the highest average score of 46.4, demonstrating
superior abstract pattern reasoning on single-concept puzzles such as numbers, colors, and size. It particularly excels
in the "Numbers" category with a score of 67.5, far surpassing other models, which may be due to its advantage in math
reasoning tasks (Yang et al., 2023). Claude 3 Opus follows with an overall average of 39.4, showing its strength in
the "Shapes" category with a top score of 44.5. The other models, including Gemini Pro and LLaVA-13B trail behind with
averages of 34.5 and 27.5 respectively, performing similarly to the random baseline on several categories.

In the evaluation on dual-concept puzzles, as shown in Table 2, GPT-4V stands out again with the highest average score
of 45.5. It performed particularly well in categories such as "Colors & Numbers" and "Colors & Size" with a score of
56.0 and 55.0 respectively. Claude 3 Opus closely follows with an average of 43.7, showing strong performance in "
Numbers & Size" with the highest score of 34.0. Interestingly, LLaVA-13B, despite its lower overall average of 31.1,
scores the highest in the "Size & Shapes" category at 39.0. Gemini Pro, on the other hand, has a more balanced
performance across categories but with a slightly lower overall average of 30.1. Overall, we find that models perform
similarly on average for single-concept and dual-concept patterns, which suggests that they are able to relate multiple
concepts such as colors and numbers together.

![](/images/results.png)

### Citation

If our work inspires your research, please cite us:

```
@article{chia2024puzzlevqa,
  title={PuzzleVQA: Diagnosing Multimodal Reasoning Challenges of Language Models with Abstract Visual Patterns},
  author={Yew Ken Chia and Vernon Toh Yan Han and Deepanway Ghosal and Lidong Bing and Soujanya Poria},
  journal={arXiv preprint arXiv:2403.13315},
  year={2024}
}
```
