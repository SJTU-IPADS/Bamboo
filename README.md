# Bamboo
We introduce Bamboo-v0.1, a new 7B LLM that boasts high sparsity while delivering performance equivalent to Mistral-7B. In this repo, we provide the details of our model.

## Models

| Model                   | Transformers(HF)                                                           | PowerInfer/llama.cpp(GGUF)                                                       |
| ----------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **Bamboo-7B-base-v0.1** | [Bamboo-base-v0.1](https://huggingface.co/PowerInfer/Bamboo-base-v0.1)     | [Bamboo-base-v0.1-gguf](https://huggingface.co/PowerInfer/Bamboo-base-v0.1-gguf) |
| **Bamboo-7B-DPO-v0.1**  | [Bamboo-DPO-v0.1](https://huggingface.co/PowerInfer/Bamboo-Bagel-DPO-v0.1) | [Bamboo-DPO-v0.1-gguf](https://huggingface.co/PowerInfer/Bamboo-DPO-v0.1-gguf)   |

## Performance with different sparsity
Recent studies([Zhang et al., 2024](https://arxiv.org/pdf/2402.03804.pdf)) has shown that the activation sparsity exists in LLMs by only keep the top-k activation neurons in each layer. In this subsection, we show the performance of Bamboo with different sparsity with the same method.

## CDF of neurons distribution
Here we show the CDF of neurons distribution of Bamboo-7B-base-v0.1.
![CDF of neurons distribution](./figures/cdf-base.pdf)

## Performance Evaluation

## Speed Evaluation

https://github.com/SJTU-IPADS/Bamboo/assets/34213478/edb1d5be-cf3e-44aa-b958-f0970ca74959

<sub>Both PowerInfer and llama.cpp fully utilized the same hardware of Intel Core i7-13700(8 threads) and Nvidia RTX 2080Ti(11G).</sub>

Below is a detailed comparison of performance gains achieved on Bamboo-7B-base with [PowerInfer](https://github.com/SJTU-IPADS/PowerInfer) and [llama.cpp](https://github.com/ggerganov/llama.cpp) across various hardware configurations.

| Scenario       | Hardware                            | with PowerInfer | with llama.cpp | Speedup |
| -------------- | ----------------------------------- | --------------- | -------------- | ------- |
| CPU+GPU Hybird | Core i7-13700(8T) + RTX 2080Ti(11G) | 33.50           | 7.60           | 4.41x   |
| Full GPU       | RTX 4090(24G)                       | 89.42           | 58.34          | 1.53x   |
| Full CPU       | Core i9-13900K(8T)                  | 9.09            | 4.78           | 1.90x   |

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
