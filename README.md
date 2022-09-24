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
  
  > Sliding window. The idea is to extend right until we meet a duplicate character. When we do, start moving the left pointer to the right and delete characters from the cache until we meet the original duplicate character.
  
  ```kt
  fun lengthOfLongestSubstring(s: String): Int {
      if (s.length == 0) return 0
      var result = 1
      var cache = HashSet<Char>()
      var l = 0; var r = 0;
      while (r < s.length) {
          if (!cache.contains(s[r])) {
              cache.add(s[r])
              result = Math.max(result, cache.size)
              r++
          } else {
              while (cache.contains(s[r])) {
                  cache.remove(s[l])
                  l++
              }
          }
      }

      return result
  }
  ```
</details>


<details>
  <summary>3. Longest Palindromic Substring (LC5)</summary>
    
  >

  ```kt
  ```
</details>
  
<details>
  <summary>1.  (LC1)</summary>

  ```kt
  ```
</details>
