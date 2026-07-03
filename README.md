# LLM Fine-Tuning for Urdu

QLoRA fine-tuning of Llama-3-8B / Mistral-7B on an Urdu instruction-following dataset.

## Why

Large language models are not trained with much Urdu data, so their instruction-following ability in Urdu is weak. This project fine-tunes an open-weight model on Urdu instruction pairs to improve that, using QLoRA to make training feasible on free-tier GPU hardware.

## Status

Planned — Year 3 of my BS. This repo currently holds the design and setup; training work begins once the dataset is ready.

## Planned approach

- Build 1,000–5,000 Urdu (instruction, response) pairs sourced from government documents and Urdu web text
- Quantize the base model to 4-bit NF4 using `bitsandbytes`
- Apply LoRA adapters (rank 16, alpha 32) with HuggingFace PEFT
- Train with the `trl` library's SFTTrainer on a Kaggle free GPU
- Evaluate on a held-out Urdu QA set against the zero-shot baseline

## Tech stack

Python, PyTorch, HuggingFace PEFT, bitsandbytes, trl, Kaggle Notebooks

## Author

Salik Hussain — github.com/salikhussain71-code

## License

MIT
```
