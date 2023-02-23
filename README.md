## Efficient Inference of Temporal Task Specifications from Human Demonstrations using Experiment Design
**Authors**: Shlok Sobti, Rahul Shome, Lydia E. Kavraki

> Increased robotic deployments in human environments have motivated the need for autonomous systems to be able to observe and interact with humans. Human demonstrations of tasks can be used to infer underlying task specifications, commonly modeled with temporal logic. State-of-the-art methods have developed Bayesian inference tools to estimate a temporal logic formula from a sequence of demonstrations. The current work proposes the introduction of experiment design to choose environments for the humans to perform demonstrations. This results in reducing the number of demonstrations needed to estimate the unknown ground truth formula with low error. A novel computationally efficient strategy is proposed by leveraging the hypothesis that the demonstrator is (near-)optimal. A human study is designed to collect 600 human demonstrations from 20 participants for 4 different tasks to validate the proposed hypothesis and empirical performance benefit over the state-of-the-art baselines. A dataset collected from the human study is also publicly shared.  

#### Instructions
The repository contains `pickle` files for each of the 4 various constraints as discussed in the paper. Additionally, we also provide anonymized survey questionnaires of the 20 participants. An example `python3` script to load this data follows:
```
import pickle
filename = 'constraint1/11_base'  # participant 1, constraint 1, baseline
data = pickle.load(open(filename, 'rb))
# extracting data
traces = data['demos']
formulae = data['formulae']
distances = data['distances']
```
As an example, to retreive the data corresponding to participant 2, constraint 3, informed case, the filename is:
```
filename = 'constraint3/23_informed'
```
Here `traces` will return 10 traces (one for each demonstration/experiment), where each trace is a sequence of truth evaluations of the predicates.
`formulae` holds the MAP estimate after each experiment, and `distances` will hold the Jaccard Distance between the current estimate and the ground truth.

The four constraints are: \
**constraint1**: $\neg blue \cup red \land \neg green \cup blue \land \neg yellow \cup green$\
**constraint2**: $\top$\
**constraint3**: $\neg green \cup blue$\
**constraint4**: $\neg green \cup blue \land \neg yellow \cup blue$
#### How to Cite
> S. Sobti, R. Shome, and L. E. Kavraki, “Efficient Inference of Temporal Task Specifications from Human Demonstrations using Experiment Design,” in Proceedings of the IEEE International Conference on Robotics and Automation, 2023.
