## Results

The file "results_flexible.csv" provides an overview of how different combinations of beam size and temperature affect the GPT-2 model’s performance on the GSM8K dataset. As the combinations of beam size and temperature change, the Values follow the same pattern. The model performs best at a beam size of 3 across all temperatures, achieving the highest score of 0.0205.

The file "plot.png" represents how the flexible extract metric varies with respect to changing beam size across all temperatures. All the five lines overlap, meaning that temperature does not affect the changes in the model’s performance, whereas beam size does. Initially, there is a sharp increase as beam size increases from 1 to 2, with the flexible extract value changing from 0.0068 to 0.019 respectively. After reaching a peak at the beam size 3 with the flexible extract value of 0.0205, the trend reverses, and the performance begins to decline. The peak at the beam size 3 implies that this is the optimal beam size for model performance on the given dataset with the chosen metric.

## Discussion

We observe that within the range of temperature values used in our experiments, temperature shows no impact on the output. However, adjusting the beam size affects the model’s performance, with a beam size of 3 consistently giving the optimal value of 0.0205 across all temperature ranges. This suggests that the beam size plays a critical role compared to the diversity introduced by temperature adjustment.
 
The consistency of performance across different seed values for identical combinations of temperature and beam size shows the stability and reproducibility of our findings. This highlights the deterministic nature of beam search strategy under controlled conditions and validates the robustness of the optimal beam size identified in our study.
 
When comparing our highest performance value of 0.0205 against the HuggingFace leaderboard, where the score of 0.68 has been reported, it is clear that there is a noticeable gap. One possible explanation for this discrepancy is the variations in hyperparameter tuning, since hyperparameters, such as learning rate, batch size, and the specific configurations of beam size and temperature can impact model performance.

Regardless, the performance of both the small and large versions of GPT-2 is quite low on the leaderboard, with the best performing models showing scores around 79. This could be due to the model's size or it being outdated, as larger and more recent models significantly outperform it. A more fundamental issue may be that GPT models are primarily designed for language generation rather than logical reasoning. It's possible that the training dataset for GPT-2 had a scarcity of mathematical problems, even though this cannot be confirmed since WebText is not fully accessible. Nonetheless, it is clear that the model was not specifically created for solving mathematical problems.

## Future work

More insights could be gained by printing and examining the output answers produced by the model, specifically to observe the format of these solutions and to understand how they are matched with the expected solutions. Unfortunately, the code from the Language Model Evaluation Harness built by EleutherAI runs in the terminal and does not generate variables for the model's outputs, but only the evaluating metrics. 

Additionally, with access to more computational resources, it would be possible to explore the potential for enhanced performance using larger models that are ranked higher in the Leaderboard. Moreover, experimenting with the number of beams across different models could also reveal whether the relation we found is consistent with bigger and more complex models.