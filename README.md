# Blind75 solutions in Kotlin

<details>
  <summary>1. Two Sum (LC1)</summary>

  ```kt
  fun twoSumHashMap(nums: IntArray, target: Int): IntArray {
      val cache = HashMap<Int, Int>()
      for ((i, value) in nums.withIndex()) {
          val existing = cache[target - value]
          if (existing != null) return intArrayOf(existing, i)
          else cache.put(value, i)
      }

      return intArrayOf()
  }
  ```
</details>


<details>
  <summary>2. Longest Substring Without Repeating Characters (LC3)</summary>

  ```kt

  ```
</details>
