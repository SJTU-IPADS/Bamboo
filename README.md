# Bamboo
We introduce Bamboo, a new 7B LLM that boasts exceptional sparsity while delivering performance equivalent to Mistral-7B. In this repo, we provide the details of our model.

## Models

| Model                   | Transformers(HF)                                                              |
|-------------------------|-------------------------------------------------------------------------------|
| **Bamboo-7B-base-v0.1** | [Bamboo-7B-base-v0.1](https://huggingface.co/PowerInfer/Bamboo-base-v0.1)     |
| **Bamboo-7B-DPO-v0.1**  | [Bamboo-7B-DPO-v0.1](https://huggingface.co/PowerInfer/Bamboo-Bagel-DPO-v0.1) |

## Performance with different sparsity
Recent studies([Zhang et al., 2024](https://arxiv.org/pdf/2402.03804.pdf)) has shown that the activation sparsity exists in LLMs by only keep the top-k activation neurons in each layer. In this subsection, we show the performance of Bamboo with different sparsity with the same method.

## CDF of neurons distribution

## Objective Performance Evaluation

## Speed Evaluation

## Limitations
* Bamboo, having undergone training with only 200B tokens, may still exhibit performance gaps in certain tasks.
* The Bamboo model has only been trained on English-language datasets, hence its capabilities in other languages are still lacking.
* The model may produce unexpected outputs due to its small size and probabilistic generation paradigm.

## Future Work

- Mixtral8*7b level sparse activation model
- Better base and chat-7B model


## Citation
Please kindly cite using the following BibTeX:

```
@misc{bamboo,
    title={Bamboo: Harmonizing Sparsity and Performance in Large Language Models}, 
    author={Yixin Song, Haotong Xie, Zeyu Mi, Haibo Chen},
    year={2024}
}
```