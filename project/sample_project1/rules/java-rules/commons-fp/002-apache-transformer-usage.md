---
description: "Guidelines for using Apache Commons Transformer, IfTransformer, and ChainedTransformer."
globs: ["**/*Service.java", "**/*Helper.java", "**/*Utils.java", "**/*Delegator.java"]
alwaysApply: false
---
Apache Commons Transformer Usage:
- Use Transformer<I, O> for single-step transformations.
- Use IfTransformer<I, O> for conditional transformations with predicates.
- Use ChainedTransformer<I, O> for sequential transformations.
- Integrate with reactive map() by wrapping in lambdas.
