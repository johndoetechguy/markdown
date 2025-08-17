---
description: "Guidelines for using Apache Commons Predicate and its implementations."
globs: ["**/*Service.java", "**/*Helper.java", "**/*Utils.java", "**/*Delegator.java"]
alwaysApply: false
---
Apache Commons Predicate Usage:
- Use Predicate<T> for boolean-valued functions.
- Use AllPredicate, AnyPredicate, NonePredicate, or OnePredicate for quantifier logic.
- Combine with AndPredicate, OrPredicate, NotPredicate for logical operations.
- Use EqualPredicate, ComparatorPredicate, InstanceofPredicate, NotNullPredicate, etc. as needed.
- Integrate with reactive filter() via lambda conversion.
