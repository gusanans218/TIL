# Aggregate Operations

```kt
val numbers = listOf(6,42,10,4)

println("Count: ${numbers.count()}") // Count: 4, 원소의 개수
println("Max: ${numbers.maxOrNull()}") // Max: 42, 원소 중 가장 큰 값
println("Min: ${numbers.minOrNull()}") // Min: 4, 원소 중 가장 작은 값
println("Average: ${numbers.average()}") // Average: 15.5, 원소들의 평균 값
println("Sum: ${numbers.sum()}") // Sum: 62, 원소들의 총합
```