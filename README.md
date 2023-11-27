## Logical Chain of Thought (LogiCot) Experiment usiong Amazon Bedrock

This repo contains an Amazon Bedrock (Using Anthropic Claude Instant v1) experiment of the paper [Enhancing Zero-Shot Chain-of-Thought Reasoning in Large Language Models through Logic](https://arxiv.org/pdf/2309.13339.pdf) also known as LogiCOT.

### High Level Paper Summary

* For scenarios requiring multi-step reasoning, LLM show hallucinations as their reasoning procedures are unconstrained by logical principles.
* Aiming to improve the zero-shot chain-of-thought reasoning ability of large language models, the authors propose Logical Chain-of-Thought (LogiCoT)
* A framework which leverages principles from symbolic logic to verify and revise the reasoning processes of LLMs

### Key Previous Related work

Built on Zero-Shot Chain of Thought paper [Large Language Models are Zero-Shot Reasoners](https://arxiv.org/abs/2205.11916) which introduced the concept of adding phrases like “Let’s think step by step” as a suffix to prompts to allow a LLM use reasoning to answer to respond to prompts

### Methodologies

**think-verify-revise**

With this framework, for every reasoning step, it adopts those who pass the verification and revise those who do not, thereby effectively improving the overall reasoning capability. 


**reductio ad absurdum**

It can be challenging to directly deduce and verify whether a reasoning is right or wrong, the authors employed a technique known as reductio ad absurdum (reduction to absurdity) to establish a claim of validation or invalidation.

> In logic, reductio ad absurdum (Latin for "reduction to absurdity"), also known as argumentum ad absurdum (Latin for "argument to absurdity") or apagogical arguments, is the form of argument that attempts to establish a claim by showing that the opposite scenario would lead to absurdity or contradiction - Wikipedia


If P denotes the premise of a conclusion
If Q denotes the conclusion 
This means there exists a proof that claims the conclusion Q given the premise P

In order to prove Q by the mean of reductio ad absurdum, let us assume its negation -Q (Opposite Scenario of Q) is valid and then check its contradiction with the premise P

Upon the contradiction of the co-existence of the P and -Q , the relationship of P and Q is thus proved true, and then we can claim the validation of the conclusion Q given the premise P.

*For Example*

*Statement: "All birds can fly."*

*Assume the Statement is True: Let's start by assuming that all birds can fly.*

*Introduce a Counterexample: Now, consider a penguin. Penguins are birds, but they cannot fly; they swim.*

*Reach an Absurd Conclusion: If all birds can fly and penguins are birds that cannot fly, this leads to an absurd or contradictory conclusion.*

*Conclude Falsity: Therefore, the initial statement "All birds can fly" must be false because it leads to an absurd outcome.*

### Experiment Notebook

Access the experiment notebook [here](LogiCOT_notebook.ipynb)


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

