Exhaustive list of methods in stream api, along with brief info as of the latest LTS version, Java 21.
These come from Java Stream API, introduced in Java 8 and expanded later.
Grouped by type of operation:

1️⃣ Stream Creation Methods
These create a Stream.
| Method                                    | Description                                   |
|-------------------------------------------|-----------------------------------------------|
| Collection.stream()                       | Creates a sequential stream from a collection |
| Collection.parallelStream()               | Creates a parallel stream                     |
| Stream.of(T...)                           | Creates stream from values                    |
| Stream.ofNullable(T)                      | Creates stream with element or empty          |
| Arrays.stream(array)                      | Creates stream from array                     |
| Stream.generate(Supplier)                 | Infinite stream using supplier                |
| Stream.iterate(seed, UnaryOperator)       | Infinite stream by applying function          |
| Stream.iterate(seed, predicate, operator) | Conditional iteration (Java 9)                |
| Stream.empty()                            | Creates empty stream                          |
| Stream.builder()                          | Creates stream builder                        |
| BufferedReader.lines()                    | Stream of lines from file                     |
| Files.lines(Path)                         | Stream lines from file                        |
