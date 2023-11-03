---
toc: true
comments: false
layout: post
title: List and Search Tech Talk Reflections
description: Team Teach Reflection
type: hacks
courses: { compsci: {week: 9} }
---
### PBL Unit 1 / Week 9
- index: organizing the data by assigning a reference value to each element
- Put the number is order either ascending or descending
- Search starts with middle number first which is found by adding the highest and lowest index number and dividing it by 2
- This divides the range by 2
- Repeat this process by shrinking the range each time till the desired target is found
- Every time the process is repeated and leads to a target it is considered a comparison
- Each element in a list is examined in the order of the first element till the desired target
- Order doesn’t matter