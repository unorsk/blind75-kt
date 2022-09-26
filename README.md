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
    
  > Sliding Window? First you iterate over the string. And for each character try to expand to the left and right while s[l] == s[r]

  ```kt
  fun longestPalindrome(s: String): String {
    var result = "";
	var maxLength = 0
    
    for (i in 0..s.length - 1) {
        var l = i; var r = i;
        while (l >= 0 && r < s.length && s[l] == s[r]) {
            if (r - l + 1 > maxLength) {
                maxLength = r - l + 1
                result = s.substring(l, r+1)
            }
            l--
            r++
        }
        
        l = i; r = i + 1;
        while (l >= 0 && r < s.length && s[l] == s[r]) {
            if (r - l + 1 > maxLength) {
                maxLength = r - l + 1
                result = s.substring(l, r+1)
            }
            l--
            r++
        }
    }
    
	return result
  }
  ```
</details>
  
<details>
  <summary>4. Counting Bits (LC338)</summary>
	
  > Significant bit changes with every power of 2.
	
  ```kt
  fun countBits(n: Int): IntArray {
    var offset = 1
    val r = IntArray(n + 1)

    for (i in 1..n) {
        if (offset * 2 == i) offset = i
        r[i] = 1 + r[i - offset]
    }

    return r
  }
  ```
</details>

<details>
  <summary>1.  (LC1)</summary>

  ```kt
  ```
</details>
