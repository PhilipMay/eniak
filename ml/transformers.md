# Transformers

## Links
- Hugging Face
  - [Hugging Face](https://huggingface.co/)
  - [Hugging Face Transformers - GitHub](https://github.com/huggingface/transformers)
  - [Hugging Face Transformers - Doc](https://huggingface.co/transformers/)
    - [Loading pre-trained weights](https://huggingface.co/transformers/serialization.html)
  -- [Hugging Face Tokenizers - GitHub](https://github.com/huggingface/tokenizers)
- FARM - Framework for Adapting Representation Models
  - [FARM - Doc](https://farm.deepset.ai/)
  - [FARM - GitHub](https://github.com/deepset-ai/FARM)
- [deepset.ai - German BERT](https://deepset.ai/german-bert)
- [Comparing Transformer Tokenizers](https://towardsdatascience.com/comparing-transformer-tokenizers-686307856955)

## Preprocessing and Tokenization
One sentence per line, and one blank line between documents. The reason for the sentence splitting is that part of the training involves a next sentence objective in which the model must predict whether two sequences of text are contiguous text from the same document or not.
