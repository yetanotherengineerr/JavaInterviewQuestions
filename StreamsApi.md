# Streams API Interview Questions
### Fundamental Stream Behavior Questions
1. What is the difference between intermediate and terminal operations?
2. Why are stream operations called lazy? 
3. What happens if you run a stream pipeline without a terminal operation?
4. Can a stream be reused after a terminal operation?
5. What exception occurs if you try to reuse a consumed stream?
6. Why is a stream not a data structure?
7. What is the difference between: collection.stream() and collection.parallelStream()
8. What is the difference between Collection API and Stream API?
9. Can streams modify the underlying collection? 
10. What is internal iteration vs external iteration?

### Intermediate Operations
11. What does peek() do, and why is it dangerous in production?
12. What is the difference between: map() & flatMap()
13. When would you use flatMap() instead of map()?
14. What happens if you call: Stream.of(1,2,3).limit(0)
15. What happens if you call: Stream.generate(() -> 1) without limit()? 
16. What does distinct() rely on internally?
17. What happens if distinct() is used on objects without equals() & hashCode()?
18. Is sorted() stable?
19. What is the complexity of sorted() in streams?
20. What is the difference between: limit() & skip()

### Terminal Operations
21. Difference between: findFirst() & findAny()
22. Why is findAny() faster in parallel streams?
23. What does count() actually do internally?
24. Difference between: forEach() & forEachOrdered()
25. When does forEach() break ordering guarantees?
26. What is the difference between: collect() & reduce()
27. When should reduce() not be used?
28. What is the identity value in reduce()? Example: reduce(0, Integer::sum)
29. What happens if the identity is incorrect?
30. Why does reduce() return Optional sometimes?

### Parallel Stream Pitfalls
31. Why can parallel streams cause performance degradation?
32. When should parallel streams not be used?
33. What thread pool do parallel streams use? Answer: ForkJoinPool.commonPool.
34. Why are stateful lambdas dangerous in parallel streams? 
Example: List<Integer> list = new ArrayList<>();
stream.parallel().forEach(list::add);
35. What problems can occur with shared mutable state?
36. Why is reduce() preferred over mutation in parallel streams?
37. What operations prevent parallel optimization?
Example:
limit()
findFirst()
38. What is the cost of splitting streams for parallel processing?
39. Why do streams work better with large datasets in parallel?
40. What is fork-join splitting in streams?

### Advanced Stream Questions
41. What is a Spliterator? Streams internally use Spliterator to split data for parallel execution.
42. What characteristics can a Spliterator have?
Examples:
ORDERED
DISTINCT
SORTED
SIZED
IMMUTABLE
43. What is short-circuiting in streams?
Examples:
findFirst()
anyMatch()
limit()
44. Why are streams single-use?
45. What happens when you modify the underlying collection during stream processing?
46. Why should IO operations inside streams be avoided?
47. What is the difference between:
stream().toList()
Collectors.toList()
Hint: immutability.
48. Why are primitive streams (IntStream, LongStream) faster?
49. What is operation fusion in streams?
50. What does this code print?
Stream.of(1,2,3,4)
.filter(x -> {
System.out.println("filter: " + x);
return x % 2 == 0;
})
.map(x -> {
System.out.println("map: " + x);
return x * 2;
})
.findFirst();

Answer concept:
Lazy evaluation → stops early.
Output roughly:
filter:1
filter:2
map:2
Stream stops after first match.
