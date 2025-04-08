# Java Maven JMH Benchmarking Project

## Introduction
This project demonstrates how to use [JMH (Java Microbenchmark Harness)](https://openjdk.org/projects/code-tools/jmh/) to benchmark Java code efficiently. JMH is a Java library developed by the same team that built the JVM and helps in writing reliable microbenchmarks.

## Prerequisites
Ensure you have the following installed:

- **Java 8+**
- **Maven 3+**

## Running the Benchmark
To generate benchmark code and run it, execute:

```sh
mvn clean install
java -jar target/benchmarks.jar
```

## Sample Benchmark Output

```sh
Benchmark                                 Mode  Cnt   Score    Error   Units
MyBenchmark.allocateLargeArrayOperation  thrpt    5  ≈ 10⁻⁵           ops/ns
MyBenchmark.stringOperation               avgt    5   0.561 ±  0.007   ns/op
```

## Set up sample project
Set up the sample project using Maven Archetype with the command.
```sh
mvn archetype:generate \
  -DinteractiveMode=false \
  -DarchetypeGroupId=org.openjdk.jmh \
  -DarchetypeArtifactId=jmh-java-benchmark-archetype \
  -DgroupId=com.example \
  -DartifactId=jmh \ 
  -Dversion=1.0
```

## Understanding JMH Modes
JMH supports multiple benchmarking modes:

- **Throughput**: Measures operations per second.
- **AverageTime**: Measures average execution time per operation.
- **SampleTime**: Measures time for individual operations and samples results.
- **SingleShotTime**: Measures time for a single operation (used for very fast operations).

You can change the mode by modifying `@BenchmarkMode(Mode.AverageTime)`.


