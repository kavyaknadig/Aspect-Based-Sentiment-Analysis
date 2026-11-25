# Introduction
Worked with a classmate on more than 10,000 student feedback comments from the public ASQE dataset and DCU student feedback. The comments covered three domains: teachers, courses and the university. Each comment already had its aspect labelled, and the models predicted whether the sentiment towards that aspect was positive, neutral or negative.

## Carried out two types of analysis:

## 1. Multi-domain: 
Trained each model on feedback from all three domains and tested it on an unseen 10% of the same data.
## 2. Cross-domain: 
Trained each model on two domains and tested it on the third, unseen domain, repeating this so each domain was tested once.

## Models compared: 
1. BERTweet
2. ModernBERT
3. LLaMA 3B
4. LLaMA 3B with LoRA (all fine-tuned)
5. Gemini 2.5 Flash (zero-shot and few-shot prompting).

# Results:

## Best overall: 
LLaMA 3B and BERTweet were effectively tied (weighted F1 0.891 and 0.890). BERTweet was much better at spotting neutral feedback (neutral F1 0.804 vs 0.627).
## Most stable across domains: 
ModernBERT barely dropped from multi-domain to cross-domain testing (0.884 to 0.881).
## Multi-domain vs cross-domain: 
multi-domain training gave better results for every model. University feedback was the easiest domain to transfer to, and course feedback was the hardest.
## Gemini: 
With no training, it reached a weighted F1 of 0.95 on university feedback. It struggled with neutral feedback (neutral F1 0.25–0.36).
## Completely new dataset: 
ModernBERT generalised best (76.7% accuracy, macro F1 0.768), and BERTweet dropped to 34.9%.
