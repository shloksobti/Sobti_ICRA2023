### Efficient Inference of Temporal Task Specifications from Human Demonstrations using Experiment Design
Shlok Sobti, Rahul Shome, Lydia E. Kavraki

> Increased robotic deployments in human environments have motivated the need for autonomous systems to be able to observe and interact with humans. Human demonstrations of tasks can be used to infer underlying task specifications, commonly modeled with temporal logic. State-of-the-art methods have developed Bayesian inference tools to estimate a temporal logic formula from a sequence of demonstrations. The current work proposes the introduction of experiment design to choose environments for the humans to perform demonstrations. This results in reducing the number of demonstrations needed to estimate the unknown ground truth formula with low error. A novel computationally efficient strategy is proposed by leveraging the hypothesis that the demonstrator is (near-)optimal. A human study is designed to collect 600 human demonstrations from 20 participants for 4 different tasks to validate the proposed hypothesis and empirical performance benefit over the state-of-the-art baselines. A dataset collected from the human study is also publicly shared.  

#### Instructions
The downloaded file contains `pickle` files for each of the 4 various constraints as discussed in the paper. Additionally, we also provide anonymized survey questionnaires of the 20 participants. An example `python3` script to load this data follows:
```
import pickle
filename = '11_base'  # constraint 1, participant 1, baseline
data = pickle.load(open(filename, 'rb))
# extracting data
traces = data['demos']
formulae = data['formulae']
distances = data['distances']
```
Here `traces` will return 10 traces (one for each demonstration/experiment), where each trace is a sequence of truth evaluations of the predicates.
`formulae` holds the MAP estimate after each experiment, and `distances` will hold the Jaccard Distance between the current estimate and the ground truth.

[Download Dataset](https://www.shlok.ai/iros2022.html)
