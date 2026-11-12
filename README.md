# BanglaDocBench

**A document-parsing benchmark for Bangla: 500 to 1,000 pages chosen for diversity from 19.9
million.**

[![Status: in development](https://img.shields.io/badge/status-in%20development-orange)](#status)
[![Dataset on Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Dataset-OpenCR--lab%2FBanglaDocBench-yellow)](https://huggingface.co/datasets/OpenCR-lab/BanglaDocBench)
[![Code licence: Apache-2.0](https://img.shields.io/badge/code-Apache--2.0-blue)](LICENSE)

BanglaDocBench will measure how well OCR and document-parsing systems read Bangla documents:
books, newspapers, government notices, textbooks, forms, old prints and modern typesetting. It
follows the approach of benchmarks such as
[OmniDocBench](https://github.com/opendatalab/OmniDocBench), for Bangla script.

## Status

**In development. No benchmark data has been released yet.** This repository and the
[Hugging Face dataset](https://huggingface.co/datasets/OpenCR-lab/BanglaDocBench) reserve the
names and will receive the code and data as each stage is finished.

## How the pages are chosen

The pages are drawn from **[BanglaDocIndex](https://huggingface.co/datasets/OpenCR-lab/BanglaDocIndex)**
([code](https://github.com/OpenCR-lab/BanglaDocIndex)), a public index of 19,873,418 Bangla
document pages with an EmbeddingGemma 2 embedding for every page.

1. **Licence filter.** Only pages whose images may be redistributed are candidates (for
   example public-domain and CC-BY pages on the Internet Archive, and NCTB textbooks).
2. **Clustering.** The page embeddings are clustered to map the kinds of pages in the pool.
3. **Selection.** Pages are sampled across clusters for diversity, with a fixed random seed.
4. **Annotation.** Each selected page is annotated (text, reading order and layout).

The selection is reproducible: the cluster labels, the selected page IDs, the seed and the
selection code will be published with the benchmark, and the selected pages will be marked in
BanglaDocIndex so that training sets can exclude them.

## Planned layout

```
selection/   clustering and page selection, from BanglaDocIndex embeddings to page IDs
eval/        evaluation code and metrics
```

## Licence

Code: [Apache-2.0](LICENSE). Annotations: CC-BY-4.0 (planned). Every page image keeps the
licence of its source document, recorded per page.

## Citation

A citation will be added with the first release.
