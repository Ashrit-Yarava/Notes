#statistics 
Cohen's Kappa is a statistical measure used to identify the agreement between two independently sampled categorical samples. This is often used as a way to measure the level of agreement between two raters for a survey. The variables must be nominal (they can be clearly distinguished between two values of the variable).

It is calcualated as follows:
$$
\kappa = \frac{p_o - p_e}{1 - p_e}
$$
where $p_o = \frac{\text{Both raters agree with each other}}{\text{Total ratings}}$ and $p_e$ is the multiplied percentages of the votes that the raters had summed together. An example is given below. Scores above 0.8 are considered substantial.

The standard error rate can be calculated as:
$$
SE(\kappa) = \sqrt{\frac{p_o(1 - p_o)}{n(1 - p_e)^2}}
$$
## Example
Two raters are identifying whether 50 patients are depressed or not. The overlap between them is shown below:

|             |               | **Rater 2** |               |     |
| ----------- | ------------- | ----------- | ------------- | --- |
|             |               | Depressed   | Not Depressed |     |
| **Rater 1** | Depressed     | 17          | 8             | 25  |
|             | Not Depressed | 6           | 19            | 25  |
|             |               | 23          | 27            | 50  |
In the above example, the calculations are as follows:
$$
p_o = \frac{17 + 19}{50} = 0.72
$$
$$
p_e = \frac{25}{50} \cdot \frac{23}{50} + \frac{25}{50} \cdot \frac{27}{50} = 0.5
$$
$$
\kappa = \frac{0.72 - 0.5}{1 - 0.5} = 0.44
$$
[Source](https://datatab.net/tutorial/cohens-kappa)
