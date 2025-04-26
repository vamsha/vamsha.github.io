---
title: LLM Model Providers & their models - Backup
layout: default
---

Here's a comparision of major Large Language Models (LLMs) 

|Model | Developer | Parameters | Specialty | Open-Source? | Cost | Efficiency | Accuracy
|:-----|:------:|:------:|:------:|:------:|:------:|:------:|-----:|
|GPT-4|OpenAI|Undisclosed|General-purpose AI, better reasoning|No|High|Moderate|Very High|
|GPT-3.5|OpenAI|175B|Text generation, chatbots|No|Moderate|Moderate|High|
|BERT|Google|340M |NLP understanding, context awareness|Yes|Free|High|High|
|LaMDA|Google|Undisclosed|Open-ended conversations|No|High|High|High|
|Claude|Anthropic|Undisclosed|Safety-focused chatbot|No|High|High|High|
|Gopher|DeepMind|280B|General NLP tasks|No|High|Moderate|High|
|Megatron-Turing NLG|NVIDIA & Microsoft|530B|Large-scale text generation|No|Very|High|Low|High
|PaLM|Google|540B|Multitasking, few-shot learning|No|Very High|Moderate|High|
|LLaMA 2|Meta AI|7B - 65B|Open-source|research model|Yes|Free|High|Moderate|
|Mistral 7B|Mistral AI|7B|Lightweight but high-performance|Yes|Free|Very|High|Moderate|




|Provider|Model|Open Source|Cost|Offline/Online|Best Use Case|Example Use Case|
|:-----|:------:|:------:|:------:|:------:|:------:|-----:|
|**OpenAI**|GPT-4, GPT-3.5|No|API-based, pricing depends on token usage|Online|Complex conversational AI, creative writing, coding assistance, and research.|ChatGPT for customer support, Codex for code generation, GPT-4 for research assistance.|
|**Anthropic**|Claude 1, Claude 2, Claude 3|No|API-based, pricing based on usage|Online|Safe, ethical AI for human-like interactions, customer support, and task automation.|Claude for ethical content moderation, chatbots in enterprise, and virtual assistants.|
|**Google DeepMind**|Gemini (Bard), PaLM|No (Gemini) / Yes (PaLM)|Cloud-based, usage-based pricing|Online|Conversational agents, information retrieval, and research-heavy applications.|Bard for search engine-like queries, PaLM for multilingual conversation systems.|
|**Mistral**|Mistral 7B, Mistral Mix, Mistral 7B Instruct|Yes (Apache 2.0)|Free to use, compute costs apply|Offline/Online|General-purpose NLP tasks, fine-tuned for instruction-based tasks.|Mistral 7B for local NLP processing in resource-constrained environments or private cloud deployments.|
|**Meta**|LLaMA, LLaMA 2|Yes (MIT)|Free to use, compute costs apply|Offline/Online|Large-scale NLP tasks, multilingual models, and research applications.|LLaMA 2 for multilingual document classification or as an open-source research tool.|
|**Cohere**|Command R|No|API-based, tiered pricing|Online|Retrieval-augmented generation, document summarization, and search optimization.|Command R for summarizing large documents in real-time for enterprise use.|
|**Hugging Face**|Transformers Library, Bloom|Yes (MIT)|Free to use, compute costs apply|	Offline/Online|Wide range of NLP tasks, translation, sentiment analysis, and text generation.|BLOOM for multilingual content generation, Hugging Face Transformers for fine-tuned NLP tasks.|
|**Cerebras**|Wafer-Scale Engine (Hardware)|No|Enterprise-level partnerships|Online (via hardware)|Large-scale AI workloads, specialized hardware for high-performance computing.|Cerebras Hardware for training large models like GPT or PaLM more efficiently on a custom infrastructure.|
|**EleutherAI**|GPT-Neo, GPT-J, GPT-NeoX|Yes (MIT)|Free to use, compute costs apply|Offline/Online|Open-source alternatives to GPT models for research, text generation, and NLP.|GPT-NeoX for running a local version of a GPT model in research environments or on-premises.|
|**xAI**|Grok|No|Subscription via X/Twitter|Online|Social media integrations, conversational agents, and content moderation.|Grok integrated into Twitter for automating responses or moderating conversations.|
|**BigScience**|BLOOM|Yes (Responsible AI License)|Free to use, compute costs apply|Offline/Online|Multilingual text generation, large-scale NLP research, and cross-lingual tasks.|BLOOM for large-scale multilingual text generation for research or enterprise applications.|
|**Aleph Alpha**|Luminous|No|API-based, enterprise pricing|Online|Multilingual NLP, AI research in Europe, and enterprise-level integrations.|Luminous for enterprise customer support with multilingual capabilities across Europe.|
