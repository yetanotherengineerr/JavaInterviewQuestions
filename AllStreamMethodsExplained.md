Exhaustive list of methods in stream api, along with brief info as of the latest LTS version, Java 21.
These come from Java Stream API, introduced in Java 8 and expanded later.
Grouped by type of operation:

### 1. Stream Creation Methods - these create a Stream.
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

### 2. Intermediate Operations (Lazy) - these transform the stream and return another stream.
#### Filtering
| Method                                    | Description                          |
|-------------------------------------------|--------------------------------------|
| filter(Predicate)                         | Keeps matching elements.             |
| Collection.parallelStream()               | Creates a parallel stream            |

#### Mapping
| Method                        | Description           |
|-------------------------------|-----------------------|
| map(Function)                 | Transform element     |
| mapToInt(ToIntFunction)       | Convert to IntStream  |
| mapToLong(ToLongFunction)     | Convert to LongStream |
| mapToDouble(ToDoubleFunction) | Convert to DoubleStr  |

#### FlatMapping
| Method                            | Description             |
|-----------------------------------|-------------------------|
| flatMap(Function)                 | Flatten nested streams  |
| flatMapToInt(ToIntFunction)       | Flatten to IntStream    |
| flatMapToLong(ToLongFunction)     | Flatten to LongStream   |
| flatMapToDouble(ToDoubleFunction) | Flatten to DoubleStream |

#### Distinct
| Method                            | Description             |
|-----------------------------------|-------------------------|
| distinct()                        | Removes Duplicates      |

#### Sorting
| Method             | Description     |
|--------------------|-----------------|
| sorted()           | Natural sorting |
| sorted(Comparator) | Custom sorting  |

#### Peek (Debugging)
| Method             | Description                               |
|--------------------|-------------------------------------------|
| peek(Consumer)     | Perform action without modifying stream   |

#### Limiting
| Method      | Description                  |
|-------------|------------------------------|
| limit(long) | Restricts number of elements |
| skip(long)  | Skips first elements         |




