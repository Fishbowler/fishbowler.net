---
title: "Testing Generative AI: The tools that still work"
date: 2023-10-14
categories : ["testing"]
layout: post
draft: true
---

When it comes to testing Generative AI, the testing industry in somewhat of a quandry. The entire IT sector is scrambling to apply AI in absolutely any way possible, and testers are left with the challenge of testing a piece of software that won’t guarantee the same output for a given set of conditions and inputs.

There are some “traditional” software testing techniques and heuristics that are still applicable despite the complexity and variability of the AI models.

## Testing Techniques that still work

1. **Regression Testing**: This technique is used to ensure that the AI model's new changes or updates do not affect its existing functionality. It is still applicable to Generative AI models since it ensures that the model's new changes do not affect its existing functionality.
2. **Boundary Value Analysis**: This technique tests the AI model's response to extreme or boundary inputs. It helps to identify the model's limitations and ensure that the model is working as intended. It is still applicable to Generative AI models since it helps to identify the model's limitations.
3. **Exploratory Testing**: This technique involves exploring the AI model's functionality and identifying any issues or bugs that may arise. It is still applicable to Generative AI models since it helps to identify any issues that may arise during the model's operation.
4. **Consistency Heuristics:** This technique involves exploring the AI and comparing it against a list of consistency oracles that we’d like it to match. Take for example, Michael Bolton’s [FEW HICCUPPS](https://developsense.com/blog/2012/07/few-hiccupps) - whilst you’d have ….

## Testing Techniques that don't work

1. Any positive test that involves an expected output.
2. **Code Coverage Testing**: This technique involves measuring the test coverage of the AI model's code. However, Generative AI models are often too complex for this technique to be effective.
3. **Static Analysis Testing**: This technique is used to identify potential issues in the AI model's code before it is executed. However, since Generative AI models are often too complex, this technique may not be effective in identifying all potential issues.
4. **Manual Testing**: This technique involves manually testing the AI model's functionality. However, since Generative AI models are often too complex, this technique may not be effective in identifying all potential issues.

In conclusion, while traditional testing techniques and heuristics still work for testing Generative AI models, some techniques may not be effective due to the complexity of the models. Therefore, it is important to choose the appropriate techniques based on the AI model's complexity and ensure that the model is thoroughly tested to guarantee its functionality.