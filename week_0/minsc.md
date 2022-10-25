# Image Retrieval for Arguments Using Stance-Aware Query Expansion

## Introduction

- they argue that images play a key role in undermining ones stance on a topic
- and that there currently isn't a search engine to look for "argumentative images"

## Related Work

## Image Retrieval for Arguments

- def: Given a keyword query suggesting an issue or a claim for a topic, retrieve as two ranked lists those and only those images that can assist someone in (1) supporting and (2) attacking it.
- results are judged based on 3 criteria: (3 levels of relevance, each criteria contains the previous one)
  - Topic Relevance: Concerns the Topic
  - Argumentativeness: Supports any Stance (no matter which one)
  - Stance relevance: Supports the stance we are actually looking for
- usually one only cares for stance relevance, but looking at all three gives more insight into errors of the method

## Stance-Aware Query Expansion

- general idea: expand user query with adjectives that imply a stance (pro, good or con, bad ...), fuse the lists in to one "pro" and one "con". If necessary, do some re-ranking
- this can be tweeked by using different underlying search engines and by choosing different expansion keywords (for example ones that depend on the query)

### Good-Anti

- expansion with "good" and "anti"
- "bad" was disregarded since it was often interpreted to mean "poorly done"

### Positive-Negative

- expansion with up to 5 positive/negative terms from the MPQA subjectivity lexicon (what is that?)

### Pros-Cons

- uses args.me to retreive positive/negative arguments for a given topic, and searches for pictures using the original query + those arguments

## Crowdsourcing Relevance Judgements

- usual TREC style evaluation, but with more categories (as mentioned above)

## Evaluation

- Nearly all images (92%-95%) relevant to the topic
  - thanks to google
  - query expansion did not seem to harm efffectiveness
- argumentative precision@10:
  - good-anti performs best (0.64)
  - pros-cons (0.52)
- when being judged for stance relevance lose 16-18%
- problem: often images are on topic, but serve more as an illustration of the topic than take a stance
- problem: with some topics (school uniforms), most results are for shopping (SEO)
- probelm: some topics are pretty one-sited, there are simply not a lot of people (publicly) argumenting in favour of animal testing

## Conclusion