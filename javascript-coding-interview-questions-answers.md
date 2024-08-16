### JavaScript Coding Round Interview Questions and Answers

#### 1. **Reverse a String**
   - **Question:** Write a JavaScript function to reverse a given string.
   - **Answer:**
     ```javascript
     function reverseString(str) {
       return str.split('').reverse().join('');
     }

     console.log(reverseString('hello')); // 'ollelo'
     ```

#### 2. **Check if a String is a Palindrome**
   - **Question:** Write a function to check if a given string is a palindrome.
   - **Answer:**
     ```javascript
     function isPalindrome(str) {
       const reversed = str.split('').reverse().join('');
       return str === reversed;
     }

     console.log(isPalindrome('madam')); // true
     console.log(isPalindrome('hello')); // false
     ```

#### 3. **Find the Factorial of a Number**
   - **Question:** Write a JavaScript function to find the factorial of a given number.
   - **Answer:**
     ```javascript
     function factorial(num) {
       if (num === 0 || num === 1) return 1;
       return num * factorial(num - 1);
     }

     console.log(factorial(5)); // 120
     ```

#### 4. **Find the Largest Number in an Array**
   - **Question:** Write a JavaScript function to find the largest number in an array.
   - **Answer:**
     ```javascript
     function findLargest(arr) {
       return Math.max(...arr);
     }

     console.log(findLargest([1, 2, 3, 4, 5])); // 5
     ```

#### 5. **Remove Duplicates from an Array**
   - **Question:** Write a JavaScript function to remove duplicates from an array.
   - **Answer:**
     ```javascript
     function removeDuplicates(arr) {
       return [...new Set(arr)];
     }

     console.log(removeDuplicates([1, 2, 3, 4, 4, 5, 5])); // [1, 2, 3, 4, 5]
     ```

#### 6. **Check if a Number is Prime**
   - **Question:** Write a JavaScript function to check if a given number is prime.
   - **Answer:**
     ```javascript
     function isPrime(num) {
       if (num <= 1) return false;
       for (let i = 2; i < num; i++) {
         if (num % i === 0) return false;
       }
       return true;
     }

     console.log(isPrime(7)); // true
     console.log(isPrime(10)); // false
     ```

#### 7. **Find the Fibonacci Sequence up to `n` terms**
   - **Question:** Write a JavaScript function to generate the Fibonacci sequence up to `n` terms.
   - **Answer:**
     ```javascript
     function fibonacci(n) {
       const sequence = [0, 1];
       for (let i = 2; i < n; i++) {
         sequence.push(sequence[i - 1] + sequence[i - 2]);
       }
       return sequence;
     }

     console.log(fibonacci(5)); // [0, 1, 1, 2, 3]
     ```

#### 8. **Sum All Numbers in a Range**
   - **Question:** Write a function that takes an array of two numbers and returns the sum of those two numbers plus the sum of all the numbers between them.
   - **Answer:**
     ```javascript
     function sumAll(arr) {
       const [min, max] = [Math.min(...arr), Math.max(...arr)];
       let sum = 0;
       for (let i = min; i <= max; i++) {
         sum += i;
       }
       return sum;
     }

     console.log(sumAll([1, 4])); // 10
     ```

#### 9. **Convert a String to Title Case**
   - **Question:** Write a JavaScript function that converts a string to title case.
   - **Answer:**
     ```javascript
     function titleCase(str) {
       return str
         .toLowerCase()
         .split(' ')
         .map(word => word.charAt(0).toUpperCase() + word.slice(1))
         .join(' ');
     }

     console.log(titleCase('I am learning javascript')); // 'I Am Learning Javascript'
     ```

#### 10. **Flatten a Nested Array**
   - **Question:** Write a JavaScript function to flatten a nested array.
   - **Answer:**
     ```javascript
     function flattenArray(arr) {
       return arr.reduce((acc, val) => Array.isArray(val) ? acc.concat(flattenArray(val)) : acc.concat(val), []);
     }

     console.log(flattenArray([1, [2, [3, [4]], 5]])); // [1, 2, 3, 4, 5]
     ```

These questions test both fundamental and more complex JavaScript coding skills, helping to assess a candidate's ability to solve problems efficiently.

### JavaScript Coding Round Interview Questions and Answers

#### 11. **Find the Intersection of Two Arrays**
   - **Question:** Write a JavaScript function to find the intersection of two arrays (i.e., elements that are present in both arrays).
   - **Answer:**
     ```javascript
     function intersection(arr1, arr2) {
       return arr1.filter(element => arr2.includes(element));
     }

     console.log(intersection([1, 2, 3, 4], [3, 4, 5, 6])); // [3, 4]
     ```

#### 12. **Sort an Array of Objects by a Property**
   - **Question:** Write a function to sort an array of objects by a specific property.
   - **Answer:**
     ```javascript
     function sortByProperty(arr, property) {
       return arr.sort((a, b) => a[property] > b[property] ? 1 : -1);
     }

     const users = [
       { name: 'Alice', age: 25 },
       { name: 'Bob', age: 20 },
       { name: 'Charlie', age: 30 }
     ];

     console.log(sortByProperty(users, 'age'));
     // [
     //   { name: 'Bob', age: 20 },
     //   { name: 'Alice', age: 25 },
     //   { name: 'Charlie', age: 30 }
     // ]
     ```

#### 13. **Remove a Specific Element from an Array**
   - **Question:** Write a JavaScript function to remove all occurrences of a specific element from an array.
   - **Answer:**
     ```javascript
     function removeElement(arr, value) {
       return arr.filter(element => element !== value);
     }

     console.log(removeElement([1, 2, 3, 4, 2, 5], 2)); // [1, 3, 4, 5]
     ```

#### 14. **Group an Array of Objects by a Property**
   - **Question:** Write a function to group an array of objects by a specific property.
   - **Answer:**
     ```javascript
     function groupBy(arr, property) {
       return arr.reduce((acc, obj) => {
         const key = obj[property];
         if (!acc[key]) {
           acc[key] = [];
         }
         acc[key].push(obj);
         return acc;
       }, {});
     }

     const people = [
       { name: 'Alice', age: 25 },
       { name: 'Bob', age: 20 },
       { name: 'Charlie', age: 25 }
     ];

     console.log(groupBy(people, 'age'));
     // {
     //   '20': [{ name: 'Bob', age: 20 }],
     //   '25': [{ name: 'Alice', age: 25 }, { name: 'Charlie', age: 25 }]
     // }
     ```

#### 15. **Find the Longest Word in a String**
   - **Question:** Write a JavaScript function to find the longest word in a given string.
   - **Answer:**
     ```javascript
     function findLongestWord(str) {
       const words = str.split(' ');
       let longestWord = '';

       words.forEach(word => {
         if (word.length > longestWord.length) {
           longestWord = word;
         }
       });

       return longestWord;
     }

     console.log(findLongestWord('The quick brown fox jumped over the lazy dog')); // 'jumped'
     ```

#### 16. **Sum of All Arguments**
   - **Question:** Write a function that returns the sum of all arguments passed to it.
   - **Answer:**
     ```javascript
     function sumOfArguments(...args) {
       return args.reduce((acc, num) => acc + num, 0);
     }

     console.log(sumOfArguments(1, 2, 3, 4)); // 10
     ```

#### 17. **Capitalize the First Letter of Each Word in a String**
   - **Question:** Write a function that capitalizes the first letter of each word in a string.
   - **Answer:**
     ```javascript
     function capitalizeWords(str) {
       return str.split(' ')
                 .map(word => word.charAt(0).toUpperCase() + word.slice(1))
                 .join(' ');
     }

     console.log(capitalizeWords('hello world from javascript')); // 'Hello World From Javascript'
     ```

#### 18. **Count the Occurrences of Each Character in a String**
   - **Question:** Write a JavaScript function that counts the occurrences of each character in a string.
   - **Answer:**
     ```javascript
     function countCharacters(str) {
       const counts = {};
       for (let char of str) {
         counts[char] = counts[char] ? counts[char] + 1 : 1;
       }
       return counts;
     }

     console.log(countCharacters('hello')); // { h: 1, e: 1, l: 2, o: 1 }
     ```

#### 19. **Check if Two Strings are Anagrams**
   - **Question:** Write a JavaScript function to check if two strings are anagrams of each other.
   - **Answer:**
     ```javascript
     function areAnagrams(str1, str2) {
       const sortString = str => str.split('').sort().join('');
       return sortString(str1) === sortString(str2);
     }

     console.log(areAnagrams('listen', 'silent')); // true
     console.log(areAnagrams('hello', 'world')); // false
     ```

#### 20. **Rotate an Array by `k` Steps**
   - **Question:** Write a function to rotate an array by `k` steps.
   - **Answer:**
     ```javascript
     function rotateArray(arr, k) {
       k = k % arr.length;
       return [...arr.slice(-k), ...arr.slice(0, -k)];
     }

     console.log(rotateArray([1, 2, 3, 4, 5], 2)); // [4, 5, 1, 2, 3]
     ```

These questions are designed to test the candidate's ability to solve common problems efficiently in JavaScript. They cover a range of concepts including arrays, strings, objects, and algorithmic thinking.

### JavaScript Coding Round Interview Questions and Answers

#### 21. **Implement a Function to Merge Two Sorted Arrays**
   - **Question:** Write a function that merges two sorted arrays into a single sorted array.
   - **Answer:**
     ```javascript
     function mergeSortedArrays(arr1, arr2) {
       let mergedArray = [];
       let i = 0, j = 0;

       while (i < arr1.length && j < arr2.length) {
         if (arr1[i] < arr2[j]) {
           mergedArray.push(arr1[i]);
           i++;
         } else {
           mergedArray.push(arr2[j]);
           j++;
         }
       }

       return mergedArray.concat(arr1.slice(i)).concat(arr2.slice(j));
     }

     console.log(mergeSortedArrays([1, 3, 5], [2, 4, 6])); // [1, 2, 3, 4, 5, 6]
     ```

#### 22. **Implement a Debounce Function**
   - **Question:** Write a JavaScript function that implements debouncing.
   - **Answer:**
     ```javascript
     function debounce(func, delay) {
       let timeout;
       return function(...args) {
         clearTimeout(timeout);
         timeout = setTimeout(() => func.apply(this, args), delay);
       };
     }

     // Example usage
     const log = debounce(() => console.log('Debounced!'), 1000);
     window.addEventListener('resize', log);
     ```

#### 23. **Find the Missing Number in an Array**
   - **Question:** Write a function to find the missing number in an array of `n` consecutive numbers.
   - **Answer:**
     ```javascript
     function findMissingNumber(arr) {
       const n = arr.length + 1;
       const total = (n * (n + 1)) / 2;
       const sum = arr.reduce((acc, num) => acc + num, 0);
       return total - sum;
     }

     console.log(findMissingNumber([1, 2, 4, 5, 6])); // 3
     ```

#### 24. **Implement a Throttle Function**
   - **Question:** Write a JavaScript function that implements throttling.
   - **Answer:**
     ```javascript
     function throttle(func, limit) {
       let inThrottle;
       return function(...args) {
         if (!inThrottle) {
           func.apply(this, args);
           inThrottle = true;
           setTimeout(() => inThrottle = false, limit);
         }
       };
     }

     // Example usage
     const log = throttle(() => console.log('Throttled!'), 1000);
     window.addEventListener('scroll', log);
     ```

#### 25. **Implement a Function to Check if a String Contains All Unique Characters**
   - **Question:** Write a JavaScript function to check if a string contains all unique characters.
   - **Answer:**
     ```javascript
     function hasUniqueCharacters(str) {
       const charSet = new Set();
       for (let char of str) {
         if (charSet.has(char)) return false;
         charSet.add(char);
       }
       return true;
     }

     console.log(hasUniqueCharacters('abcdef')); // true
     console.log(hasUniqueCharacters('hello')); // false
     ```

#### 26. **Implement a Function to Get the Nth Fibonacci Number**
   - **Question:** Write a JavaScript function to get the nth Fibonacci number.
   - **Answer:**
     ```javascript
     function getNthFibonacci(n) {
       if (n <= 1) return n;
       let a = 0, b = 1, temp;
       for (let i = 2; i <= n; i++) {
         temp = a + b;
         a = b;
         b = temp;
       }
       return b;
     }

     console.log(getNthFibonacci(7)); // 13
     ```

#### 27. **Implement a Function to Perform Binary Search**
   - **Question:** Write a JavaScript function to perform binary search on a sorted array.
   - **Answer:**
     ```javascript
     function binarySearch(arr, target) {
       let left = 0;
       let right = arr.length - 1;

       while (left <= right) {
         const mid = Math.floor((left + right) / 2);
         if (arr[mid] === target) return mid;
         if (arr[mid] < target) left = mid + 1;
         else right = mid - 1;
       }

       return -1;
     }

     console.log(binarySearch([1, 2, 3, 4, 5, 6], 4)); // 3
     console.log(binarySearch([1, 2, 3, 4, 5, 6], 7)); // -1
     ```

#### 28. **Flatten an Object with Nested Properties**
   - **Question:** Write a JavaScript function to flatten an object with nested properties.
   - **Answer:**
     ```javascript
     function flattenObject(obj, parent = '', res = {}) {
       for (let key in obj) {
         const propName = parent ? `${parent}.${key}` : key;
         if (typeof obj[key] === 'object' && !Array.isArray(obj[key])) {
           flattenObject(obj[key], propName, res);
         } else {
           res[propName] = obj[key];
         }
       }
       return res;
     }

     const obj = {
       a: 1,
       b: {
         c: 2,
         d: {
           e: 3
         }
       }
     };

     console.log(flattenObject(obj));
     // { 'a': 1, 'b.c': 2, 'b.d.e': 3 }
     ```

#### 29. **Implement a Function to Deep Clone an Object**
   - **Question:** Write a JavaScript function to deep clone an object.
   - **Answer:**
     ```javascript
     function deepClone(obj) {
       if (obj === null || typeof obj !== 'object') return obj;
       if (Array.isArray(obj)) return obj.map(deepClone);
       const clonedObj = {};
       for (let key in obj) {
         clonedObj[key] = deepClone(obj[key]);
       }
       return clonedObj;
     }

     const original = { a: 1, b: { c: 2 } };
     const copy = deepClone(original);
     console.log(copy); // { a: 1, b: { c: 2 } }
     console.log(copy === original); // false
     ```

#### 30. **Implement a Function to Find the First Non-Repeating Character in a String**
   - **Question:** Write a JavaScript function to find the first non-repeating character in a string.
   - **Answer:**
     ```javascript
     function firstNonRepeatingChar(str) {
       const charCount = {};

       for (let char of str) {
         charCount[char] = (charCount[char] || 0) + 1;
       }

       for (let char of str) {
         if (charCount[char] === 1) {
           return char;
         }
       }

       return null;
     }

     console.log(firstNonRepeatingChar('swiss')); // 'w'
     ```

These questions test a variety of skills including array manipulation, function creation, recursion, and understanding of JavaScript's object handling. They are designed to gauge a candidate's problem-solving abilities and understanding of key JavaScript concepts.

### JavaScript Coding Round Interview Questions and Answers

#### 31. **Implement a Function to Find the Largest Sum of Contiguous Subarray (Kadane’s Algorithm)**
   - **Question:** Write a JavaScript function to find the largest sum of a contiguous subarray within a given array.
   - **Answer:**
     ```javascript
     function maxSubArraySum(arr) {
       let maxSoFar = arr[0];
       let maxEndingHere = arr[0];

       for (let i = 1; i < arr.length; i++) {
         maxEndingHere = Math.max(arr[i], maxEndingHere + arr[i]);
         maxSoFar = Math.max(maxSoFar, maxEndingHere);
       }

       return maxSoFar;
     }

     console.log(maxSubArraySum([-2, 1, -3, 4, -1, 2, 1, -5, 4])); // 6 (subarray: [4, -1, 2, 1])
     ```

#### 32. **Implement a Function to Find the Longest Palindromic Substring**
   - **Question:** Write a JavaScript function to find the longest palindromic substring in a given string.
   - **Answer:**
     ```javascript
     function longestPalindrome(s) {
       if (s.length <= 1) return s;

       let start = 0, maxLength = 1;

       function expandAroundCenter(left, right) {
         while (left >= 0 && right < s.length && s[left] === s[right]) {
           if (right - left + 1 > maxLength) {
             start = left;
             maxLength = right - left + 1;
           }
           left--;
           right++;
         }
       }

       for (let i = 0; i < s.length; i++) {
         expandAroundCenter(i, i);       // Odd-length palindromes
         expandAroundCenter(i, i + 1);   // Even-length palindromes
       }

       return s.slice(start, start + maxLength);
     }

     console.log(longestPalindrome('babad')); // 'bab' or 'aba'
     ```

#### 33. **Implement a Function to Check if a Number is Prime**
   - **Question:** Write a JavaScript function to check if a number is prime.
   - **Answer:**
     ```javascript
     function isPrime(n) {
       if (n <= 1) return false;
       if (n <= 3) return true;

       if (n % 2 === 0 || n % 3 === 0) return false;

       for (let i = 5; i * i <= n; i += 6) {
         if (n % i === 0 || n % (i + 2) === 0) return false;
       }

       return true;
     }

     console.log(isPrime(11)); // true
     console.log(isPrime(25)); // false
     ```

#### 34. **Implement a Function to Generate All Permutations of a String**
   - **Question:** Write a JavaScript function to generate all permutations of a given string.
   - **Answer:**
     ```javascript
     function permute(str) {
       if (str.length === 0) return [''];
       let result = [];

       for (let i = 0; i < str.length; i++) {
         let rest = permute(str.slice(0, i) + str.slice(i + 1));
         for (let perm of rest) {
           result.push(str[i] + perm);
         }
       }

       return result;
     }

     console.log(permute('abc')); // ['abc', 'acb', 'bac', 'bca', 'cab', 'cba']
     ```

#### 35. **Implement a Function to Calculate the Power of a Number (x^n)**
   - **Question:** Write a JavaScript function to calculate the power of a number (x^n) using recursion.
   - **Answer:**
     ```javascript
     function power(x, n) {
       if (n === 0) return 1;
       if (n < 0) return 1 / power(x, -n);
       if (n % 2 === 0) {
         let half = power(x, n / 2);
         return half * half;
       }
       return x * power(x, n - 1);
     }

     console.log(power(2, 3)); // 8
     console.log(power(2, -3)); // 0.125
     ```

#### 36. **Implement a Function to Find the Median of Two Sorted Arrays**
   - **Question:** Write a JavaScript function to find the median of two sorted arrays.
   - **Answer:**
     ```javascript
     function findMedianSortedArrays(nums1, nums2) {
       let merged = nums1.concat(nums2).sort((a, b) => a - b);
       let len = merged.length;
       if (len % 2 === 0) {
         return (merged[len / 2 - 1] + merged[len / 2]) / 2;
       } else {
         return merged[Math.floor(len / 2)];
       }
     }

     console.log(findMedianSortedArrays([1, 3], [2])); // 2
     console.log(findMedianSortedArrays([1, 2], [3, 4])); // 2.5
     ```

#### 37. **Implement a Function to Find the Maximum Product of Two Integers in an Array**
   - **Question:** Write a JavaScript function to find the maximum product of two integers in an array.
   - **Answer:**
     ```javascript
     function maxProduct(arr) {
       if (arr.length < 2) return null;
       arr.sort((a, b) => a - b);
       return Math.max(arr[0] * arr[1], arr[arr.length - 1] * arr[arr.length - 2]);
     }

     console.log(maxProduct([1, 20, 3, 10, 9, 0, -1])); // 200
     ```

#### 38. **Implement a Function to Convert a Roman Numeral to an Integer**
   - **Question:** Write a JavaScript function to convert a Roman numeral to an integer.
   - **Answer:**
     ```javascript
     function romanToInt(s) {
       const romanMap = {
         'I': 1,
         'V': 5,
         'X': 10,
         'L': 50,
         'C': 100,
         'D': 500,
         'M': 1000
       };

       let total = 0;
       for (let i = 0; i < s.length; i++) {
         let current = romanMap[s[i]];
         let next = romanMap[s[i + 1]];

         if (next && current < next) {
           total -= current;
         } else {
           total += current;
         }
       }

       return total;
     }

     console.log(romanToInt('IX')); // 9
     console.log(romanToInt('LVIII')); // 58
     ```

#### 39. **Implement a Function to Calculate the GCD of Two Numbers**
   - **Question:** Write a JavaScript function to calculate the greatest common divisor (GCD) of two numbers.
   - **Answer:**
     ```javascript
     function gcd(a, b) {
       if (b === 0) return a;
       return gcd(b, a % b);
     }

     console.log(gcd(54, 24)); // 6
     ```

#### 40. **Implement a Function to Merge Intervals**
   - **Question:** Write a JavaScript function to merge overlapping intervals.
   - **Answer:**
     ```javascript
     function mergeIntervals(intervals) {
       if (!intervals.length) return [];
       intervals.sort((a, b) => a[0] - b[0]);

       let result = [intervals[0]];

       for (let i = 1; i < intervals.length; i++) {
         let current = result[result.length - 1];
         let next = intervals[i];

         if (current[1] >= next[0]) {
           current[1] = Math.max(current[1], next[1]);
         } else {
           result.push(next);
         }
       }

       return result;
     }

     console.log(mergeIntervals([[1, 3], [2, 6], [8, 10], [15, 18]]));
     // [[1, 6], [8, 10], [15, 18]]
     ```

These coding questions assess the candidate's ability to implement various algorithms and solve complex problems using JavaScript. They cover important topics such as string manipulation, array handling, recursion, and mathematical algorithms.

### JavaScript Coding Round Interview Questions and Answers

#### 41. **Implement a Function to Perform Depth-First Search (DFS) on a Graph**
   - **Question:** Write a JavaScript function to perform Depth-First Search (DFS) on a graph.
   - **Answer:**
     ```javascript
     function dfs(graph, start) {
       let visited = new Set();
       let result = [];

       function traverse(vertex) {
         if (!vertex || visited.has(vertex)) return;
         visited.add(vertex);
         result.push(vertex);

         graph[vertex].forEach(neighbor => {
           traverse(neighbor);
         });
       }

       traverse(start);
       return result;
     }

     const graph = {
       A: ['B', 'C'],
       B: ['D', 'E'],
       C: ['F'],
       D: [],
       E: ['F'],
       F: []
     };

     console.log(dfs(graph, 'A')); // ['A', 'B', 'D', 'E', 'F', 'C']
     ```

#### 42. **Implement a Function to Perform Breadth-First Search (BFS) on a Graph**
   - **Question:** Write a JavaScript function to perform Breadth-First Search (BFS) on a graph.
   - **Answer:**
     ```javascript
     function bfs(graph, start) {
       let visited = new Set();
       let queue = [start];
       let result = [];

       while (queue.length) {
         let vertex = queue.shift();
         if (!visited.has(vertex)) {
           visited.add(vertex);
           result.push(vertex);
           graph[vertex].forEach(neighbor => {
             queue.push(neighbor);
           });
         }
       }

       return result;
     }

     const graph = {
       A: ['B', 'C'],
       B: ['D', 'E'],
       C: ['F'],
       D: [],
       E: ['F'],
       F: []
     };

     console.log(bfs(graph, 'A')); // ['A', 'B', 'C', 'D', 'E', 'F']
     ```

#### 43. **Implement a Function to Flatten a Nested Array**
   - **Question:** Write a JavaScript function to flatten a nested array.
   - **Answer:**
     ```javascript
     function flattenArray(arr) {
       return arr.reduce((flat, toFlatten) => {
         return flat.concat(Array.isArray(toFlatten) ? flattenArray(toFlatten) : toFlatten);
       }, []);
     }

     console.log(flattenArray([1, [2, [3, [4, 5]]]])); // [1, 2, 3, 4, 5]
     ```

#### 44. **Implement a Function to Find the First Non-Repeating Character in a String**
   - **Question:** Write a JavaScript function to find the first non-repeating character in a string.
   - **Answer:**
     ```javascript
     function firstNonRepeatingChar(str) {
       let charCount = {};

       for (let char of str) {
         charCount[char] = (charCount[char] || 0) + 1;
       }

       for (let char of str) {
         if (charCount[char] === 1) {
           return char;
         }
       }

       return null;
     }

     console.log(firstNonRepeatingChar('swiss')); // 'w'
     ```

#### 45. **Implement a Function to Rotate a Matrix by 90 Degrees**
   - **Question:** Write a JavaScript function to rotate an NxN matrix by 90 degrees.
   - **Answer:**
     ```javascript
     function rotateMatrix(matrix) {
       const n = matrix.length;

       for (let i = 0; i < n / 2; i++) {
         for (let j = i; j < n - i - 1; j++) {
           let temp = matrix[i][j];
           matrix[i][j] = matrix[n - j - 1][i];
           matrix[n - j - 1][i] = matrix[n - i - 1][n - j - 1];
           matrix[n - i - 1][n - j - 1] = matrix[j][n - i - 1];
           matrix[j][n - i - 1] = temp;
         }
       }

       return matrix;
     }

     const matrix = [
       [1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]
     ];

     console.log(rotateMatrix(matrix));
     // [
     //   [7, 4, 1],
     //   [8, 5, 2],
     //   [9, 6, 3]
     // ]
     ```

#### 46. **Implement a Function to Merge Two Sorted Arrays**
   - **Question:** Write a JavaScript function to merge two sorted arrays into one sorted array.
   - **Answer:**
     ```javascript
     function mergeSortedArrays(arr1, arr2) {
       let merged = [];
       let i = 0, j = 0;

       while (i < arr1.length && j < arr2.length) {
         if (arr1[i] < arr2[j]) {
           merged.push(arr1[i]);
           i++;
         } else {
           merged.push(arr2[j]);
           j++;
         }
       }

       return merged.concat(arr1.slice(i)).concat(arr2.slice(j));
     }

     console.log(mergeSortedArrays([1, 3, 5], [2, 4, 6])); // [1, 2, 3, 4, 5, 6]
     ```

#### 47. **Implement a Function to Find the Intersection of Two Arrays**
   - **Question:** Write a JavaScript function to find the intersection of two arrays.
   - **Answer:**
     ```javascript
     function arrayIntersection(arr1, arr2) {
       let set1 = new Set(arr1);
       let set2 = new Set(arr2);
       let intersection = [...set1].filter(item => set2.has(item));
       return intersection;
     }

     console.log(arrayIntersection([1, 2, 2, 1], [2, 2])); // [2]
     ```

#### 48. **Implement a Function to Remove Duplicates from a Sorted Array**
   - **Question:** Write a JavaScript function to remove duplicates from a sorted array.
   - **Answer:**
     ```javascript
     function removeDuplicates(arr) {
       let uniqueArr = [];

       for (let i = 0; i < arr.length; i++) {
         if (i === 0 || arr[i] !== arr[i - 1]) {
           uniqueArr.push(arr[i]);
         }
       }

       return uniqueArr;
     }

     console.log(removeDuplicates([1, 1, 2, 2, 3, 4, 4, 5])); // [1, 2, 3, 4, 5]
     ```

#### 49. **Implement a Function to Reverse a Linked List**
   - **Question:** Write a JavaScript function to reverse a singly linked list.
   - **Answer:**
     ```javascript
     class ListNode {
       constructor(val) {
         this.val = val;
         this.next = null;
       }
     }

     function reverseLinkedList(head) {
       let prev = null;
       let current = head;
       let next = null;

       while (current !== null) {
         next = current.next;
         current.next = prev;
         prev = current;
         current = next;
       }

       return prev;
     }

     let head = new ListNode(1);
     head.next = new ListNode(2);
     head.next.next = new ListNode(3);

     let reversedHead = reverseLinkedList(head);
     console.log(reversedHead.val); // 3
     ```

#### 50. **Implement a Function to Generate All Subsets of a Set**
   - **Question:** Write a JavaScript function to generate all subsets of a given set (array).
   - **Answer:**
     ```javascript
     function generateSubsets(arr) {
       let result = [[]];

       for (let i = 0; i < arr.length; i++) {
         let current = [];
         for (let j = 0; j < result.length; j++) {
           current.push(result[j].concat(arr[i]));
         }
         result = result.concat(current);
       }

       return result;
     }

     console.log(generateSubsets([1, 2, 3]));
     // [[], [1], [2], [3], [1, 2], [1, 3], [2, 3], [1, 2, 3]]
     ```

These coding questions require the candidate to demonstrate a solid understanding of algorithms, data structures, and problem-solving techniques in JavaScript. They cover essential topics like graph traversal, array manipulation, recursion, and linked lists.

### JavaScript Coding Round Interview Questions and Answers

#### 61. **Implement a Function to Find the Longest Palindromic Substring in a String**
   - **Question:** Write a JavaScript function to find the longest palindromic substring in a given string.
   - **Answer:**
     ```javascript
     function longestPalindrome(s) {
       let longest = '';

       function expandAroundCenter(s, left, right) {
         while (left >= 0 && right < s.length && s[left] === s[right]) {
           left--;
           right++;
         }
         return s.slice(left + 1, right);
       }

       for (let i = 0; i < s.length; i++) {
         let oddPalindrome = expandAroundCenter(s, i, i);
         let evenPalindrome = expandAroundCenter(s, i, i + 1);
         let currentLongest = oddPalindrome.length > evenPalindrome.length ? oddPalindrome : evenPalindrome;
         if (currentLongest.length > longest.length) {
           longest = currentLongest;
         }
       }

       return longest;
     }

     console.log(longestPalindrome("babad")); // "bab" or "aba"
     ```

#### 62. **Implement a Function to Check if Two Strings are Anagrams**
   - **Question:** Write a JavaScript function to check if two strings are anagrams of each other.
   - **Answer:**
     ```javascript
     function areAnagrams(str1, str2) {
       if (str1.length !== str2.length) return false;

       let count = {};

       for (let i = 0; i < str1.length; i++) {
         count[str1[i]] = (count[str1[i]] || 0) + 1;
         count[str2[i]] = (count[str2[i]] || 0) - 1;
       }

       return Object.values(count).every(val => val === 0);
     }

     console.log(areAnagrams("listen", "silent")); // true
     console.log(areAnagrams("hello", "world")); // false
     ```

#### 63. **Implement a Function to Find the Maximum Subarray Sum (Kadane's Algorithm)**
   - **Question:** Write a JavaScript function to find the maximum sum of a contiguous subarray within a one-dimensional numeric array.
   - **Answer:**
     ```javascript
     function maxSubArray(nums) {
       let maxSum = nums[0];
       let currentSum = nums[0];

       for (let i = 1; i < nums.length; i++) {
         currentSum = Math.max(nums[i], currentSum + nums[i]);
         maxSum = Math.max(maxSum, currentSum);
       }

       return maxSum;
     }

     console.log(maxSubArray([-2, 1, -3, 4, -1, 2, 1, -5, 4])); // 6
     ```

#### 64. **Implement a Function to Check if a String is a Valid Parentheses**
   - **Question:** Write a JavaScript function to check if a string containing only parentheses is valid.
   - **Answer:**
     ```javascript
     function isValidParentheses(s) {
       let stack = [];
       let map = {
         '(': ')',
         '[': ']',
         '{': '}'
       };

       for (let i = 0; i < s.length; i++) {
         if (map[s[i]]) {
           stack.push(map[s[i]]);
         } else if (stack.length > 0 && stack[stack.length - 1] === s[i]) {
           stack.pop();
         } else {
           return false;
         }
       }

       return stack.length === 0;
     }

     console.log(isValidParentheses("()[]{}")); // true
     console.log(isValidParentheses("(]")); // false
     ```

#### 65. **Implement a Function to Generate All Permutations of an Array**
   - **Question:** Write a JavaScript function to generate all permutations of an array of unique elements.
   - **Answer:**
     ```javascript
     function permute(nums) {
       let result = [];

       function backtrack(path, options) {
         if (path.length === nums.length) {
           result.push([...path]);
           return;
         }

         for (let i = 0; i < options.length; i++) {
           path.push(options[i]);
           backtrack(path, options.filter((_, index) => index !== i));
           path.pop();
         }
       }

       backtrack([], nums);
       return result;
     }

     console.log(permute([1, 2, 3]));
     // [
     //   [1, 2, 3],
     //   [1, 3, 2],
     //   [2, 1, 3],
     //   [2, 3, 1],
     //   [3, 1, 2],
     //   [3, 2, 1]
     // ]
     ```

#### 66. **Implement a Function to Merge Intervals**
   - **Question:** Write a JavaScript function to merge overlapping intervals in a list of intervals.
   - **Answer:**
     ```javascript
     function mergeIntervals(intervals) {
       if (!intervals.length) return [];

       intervals.sort((a, b) => a[0] - b[0]);

       let result = [intervals[0]];

       for (let i = 1; i < intervals.length; i++) {
         let current = intervals[i];
         let last = result[result.length - 1];

         if (current[0] <= last[1]) {
           last[1] = Math.max(last[1], current[1]);
         } else {
           result.push(current);
         }
       }

       return result;
     }

     console.log(mergeIntervals([[1, 3], [2, 6], [8, 10], [15, 18]]));
     // [[1, 6], [8, 10], [15, 18]]
     ```

#### 67. **Implement a Function to Find the Kth Largest Element in an Array**
   - **Question:** Write a JavaScript function to find the kth largest element in an unsorted array.
   - **Answer:**
     ```javascript
     function findKthLargest(nums, k) {
       nums.sort((a, b) => b - a);
       return nums[k - 1];
     }

     console.log(findKthLargest([3, 2, 1, 5, 6, 4], 2)); // 5
     ```

#### 68. **Implement a Function to Find the Majority Element in an Array**
   - **Question:** Write a JavaScript function to find the majority element in an array (an element that appears more than n/2 times).
   - **Answer:**
     ```javascript
     function majorityElement(nums) {
       let count = 0;
       let candidate = null;

       for (let num of nums) {
         if (count === 0) {
           candidate = num;
         }
         count += (num === candidate) ? 1 : -1;
       }

       return candidate;
     }

     console.log(majorityElement([3, 2, 3])); // 3
     console.log(majorityElement([2, 2, 1, 1, 1, 2, 2])); // 2
     ```

#### 69. **Implement a Function to Perform Binary Search on a Sorted Array**
   - **Question:** Write a JavaScript function to perform binary search on a sorted array and return the index of the target element.
   - **Answer:**
     ```javascript
     function binarySearch(arr, target) {
       let left = 0;
       let right = arr.length - 1;

       while (left <= right) {
         let mid = Math.floor((left + right) / 2);

         if (arr[mid] === target) {
           return mid;
         } else if (arr[mid] < target) {
           left = mid + 1;
         } else {
           right = mid - 1;
         }
       }

       return -1;
     }

     console.log(binarySearch([1, 2, 3, 4, 5, 6], 4)); // 3
     console.log(binarySearch([1, 2, 3, 4, 5, 6], 7)); // -1
     ```

#### 70. **Implement a Function to Find the Minimum in a Rotated Sorted Array**
   - **Question:** Write a JavaScript function to find the minimum element in a rotated sorted array.
   - **Answer:**
     ```javascript
     function findMinInRotatedArray(nums) {
       let left = 0;
       let right = nums.length - 1;

       while (left < right) {
         let mid = Math.floor((left + right) / 2);

         if (nums[mid] > nums[right]) {
           left = mid + 1;
         } else {
           right = mid;
         }
       }

       return nums[left];
     }

     console.log(findMinInRotatedArray([3, 4, 5, 1, 2])); // 1
     console.log(findMinInRotatedArray([4, 5, 6, 7, 0, 1, 2])); // 0
     ```

These questions focus on fundamental algorithms and problem-solving techniques that are crucial for coding interviews in JavaScript. They cover topics like string

### JavaScript Coding Round Interview Questions and Answers

#### 71. **Implement a Function to Reverse Nodes in k-Group in a Linked List**
   - **Question:** Write a JavaScript function to reverse nodes in k-group in a linked list.
   - **Answer:**
     ```javascript
     class ListNode {
       constructor(val, next = null) {
         this.val = val;
         this.next = next;
       }
     }

     function reverseKGroup(head, k) {
       let count = 0;
       let node = head;

       while (node && count !== k) {
         node = node.next;
         count++;
       }

       if (count === k) {
         node = reverseKGroup(node, k);

         while (count-- > 0) {
           let temp = head.next;
           head.next = node;
           node = head;
           head = temp;
         }

         head = node;
       }

       return head;
     }

     // Helper function to print linked list
     function printList(head) {
       let result = [];
       while (head) {
         result.push(head.val);
         head = head.next;
       }
       console.log(result.join('->'));
     }

     // Example usage
     let list = new ListNode(1, new ListNode(2, new ListNode(3, new ListNode(4, new ListNode(5)))));
     let newHead = reverseKGroup(list, 2);
     printList(newHead); // 2->1->4->3->5
     ```

#### 72. **Implement a Function to Serialize and Deserialize a Binary Tree**
   - **Question:** Write a JavaScript function to serialize and deserialize a binary tree.
   - **Answer:**
     ```javascript
     class TreeNode {
       constructor(val, left = null, right = null) {
         this.val = val;
         this.left = left;
         this.right = right;
       }
     }

     function serialize(root) {
       const result = [];

       function dfs(node) {
         if (!node) {
           result.push('null');
           return;
         }
         result.push(node.val);
         dfs(node.left);
         dfs(node.right);
       }

       dfs(root);
       return result.join(',');
     }

     function deserialize(data) {
       const values = data.split(',');

       function buildTree() {
         const val = values.shift();
         if (val === 'null') return null;
         const node = new TreeNode(Number(val));
         node.left = buildTree();
         node.right = buildTree();
         return node;
       }

       return buildTree();
     }

     // Example usage
     let tree = new TreeNode(1, new TreeNode(2), new TreeNode(3, new TreeNode(4), new TreeNode(5)));
     let data = serialize(tree);
     console.log(data); // "1,2,null,null,3,4,null,null,5,null,null"
     let newTree = deserialize(data);
     console.log(serialize(newTree)); // "1,2,null,null,3,4,null,null,5,null,null"
     ```

#### 73. **Implement a Function to Rotate an Image (Matrix) by 90 Degrees**
   - **Question:** Write a JavaScript function to rotate a 2D matrix by 90 degrees clockwise.
   - **Answer:**
     ```javascript
     function rotateMatrix(matrix) {
       const n = matrix.length;

       for (let i = 0; i < n; i++) {
         for (let j = i; j < n; j++) {
           [matrix[i][j], matrix[j][i]] = [matrix[j][i], matrix[i][j]];
         }
       }

       for (let i = 0; i < n; i++) {
         matrix[i].reverse();
       }

       return matrix;
     }

     // Example usage
     let matrix = [
       [1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]
     ];
     rotateMatrix(matrix);
     console.log(matrix);
     // [
     //   [7, 4, 1],
     //   [8, 5, 2],
     //   [9, 6, 3]
     // ]
     ```

#### 74. **Implement a Function to Find All Unique Combinations that Sum to a Target**
   - **Question:** Write a JavaScript function to find all unique combinations in an array where the elements sum to a given target.
   - **Answer:**
     ```javascript
     function combinationSum(candidates, target) {
       const result = [];

       function backtrack(remain, path, start) {
         if (remain === 0) {
           result.push([...path]);
           return;
         }

         for (let i = start; i < candidates.length; i++) {
           if (candidates[i] > remain) continue;
           path.push(candidates[i]);
           backtrack(remain - candidates[i], path, i);
           path.pop();
         }
       }

       backtrack(target, [], 0);
       return result;
     }

     // Example usage
     console.log(combinationSum([2, 3, 6, 7], 7)); // [[7], [2, 2, 3]]
     ```

#### 75. **Implement a Function to Generate the Spiral Order of a Matrix**
   - **Question:** Write a JavaScript function to return the elements of a 2D matrix in spiral order.
   - **Answer:**
     ```javascript
     function spiralOrder(matrix) {
       const result = [];
       let left = 0, right = matrix[0].length - 1;
       let top = 0, bottom = matrix.length - 1;

       while (left <= right && top <= bottom) {
         for (let i = left; i <= right; i++) result.push(matrix[top][i]);
         top++;
         for (let i = top; i <= bottom; i++) result.push(matrix[i][right]);
         right--;
         if (top <= bottom) {
           for (let i = right; i >= left; i--) result.push(matrix[bottom][i]);
           bottom--;
         }
         if (left <= right) {
           for (let i = bottom; i >= top; i--) result.push(matrix[i][left]);
           left++;
         }
       }

       return result;
     }

     // Example usage
     let matrix = [
       [1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]
     ];
     console.log(spiralOrder(matrix)); // [1, 2, 3, 6, 9, 8, 7, 4, 5]
     ```

#### 76. **Implement a Function to Find the Number of Islands in a 2D Grid**
   - **Question:** Write a JavaScript function to find the number of islands in a 2D grid (1 represents land and 0 represents water).
   - **Answer:**
     ```javascript
     function numIslands(grid) {
       if (!grid.length) return 0;

       let count = 0;

       function dfs(i, j) {
         if (i < 0 || i >= grid.length || j < 0 || j >= grid[0].length || grid[i][j] === '0') return;
         grid[i][j] = '0';
         dfs(i + 1, j);
         dfs(i - 1, j);
         dfs(i, j + 1);
         dfs(i, j - 1);
       }

       for (let i = 0; i < grid.length; i++) {
         for (let j = 0; j < grid[0].length; j++) {
           if (grid[i][j] === '1') {
             count++;
             dfs(i, j);
           }
         }
       }

       return count;
     }

     // Example usage
     const grid = [
       ['1', '1', '0', '0', '0'],
       ['1', '1', '0', '0', '0'],
       ['0', '0', '1', '0', '0'],
       ['0', '0', '0', '1', '1']
     ];
     console.log(numIslands(grid)); // 3
     ```

#### 77. **Implement a Function to Check if a Number is Happy**
   - **Question:** Write a JavaScript function to determine if a number is "happy." A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1, or it loops endlessly in a cycle that does not include 1.
   - **Answer:**
     ```javascript
     function isHappy(n) {
       const seen = new Set();

       while (n !== 1 && !seen.has(n)) {
         seen.add(n);
         n = String(n).split('').reduce((sum, digit) => sum + digit * digit, 0);
       }

       return n === 1;
     }

     console.log(isHappy(19)); // true
     console.log(isHappy(2)); // false
     ```

### JavaScript Coding Round Interview Questions and Answers

#### 78. **Implement a Function to Find the Single Non-Duplicate Element in a Sorted Array**
   - **Question:** Write a JavaScript function to find the single element in a sorted array that appears only once.
   - **Answer:**
     ```javascript
     function singleNonDuplicate(nums) {
       let left = 0;
       let right = nums.length - 1;

       while (left < right) {
         let mid = Math.floor((left + right) / 2);
         if (mid % 2 === 1) mid--; // Ensure mid is even
         
         if (nums[mid] === nums[mid + 1]) {
           left = mid + 2;
         } else {
           right = mid;
         }
       }

       return nums[left];
     }

     // Example usage
     console.log(singleNonDuplicate([1, 1, 2, 3, 3, 4, 4, 8, 8])); // 2
     console.log(singleNonDuplicate([3, 3, 7, 7, 10, 11, 11])); // 10
     ```

#### 79. **Implement a Function to Merge Two Sorted Arrays**
   - **Question:** Write a JavaScript function to merge two sorted arrays into one sorted array.
   - **Answer:**
     ```javascript
     function mergeSortedArrays(nums1, nums2) {
       let mergedArray = [];
       let i = 0, j = 0;

       while (i < nums1.length && j < nums2.length) {
         if (nums1[i] < nums2[j]) {
           mergedArray.push(nums1[i]);
           i++;
         } else {
           mergedArray.push(nums2[j]);
           j++;
         }
       }

       while (i < nums1.length) {
         mergedArray.push(nums1[i]);
         i++;
       }

       while (j < nums2.length) {
         mergedArray.push(nums2[j]);
         j++;
       }

       return mergedArray;
     }

     // Example usage
     console.log(mergeSortedArrays([1, 3, 5], [2, 4, 6])); // [1, 2, 3, 4, 5, 6]
     console.log(mergeSortedArrays([0, 3, 4], [1, 2, 5])); // [0, 1, 2, 3, 4, 5]
     ```

#### 80. **Implement a Function to Generate All Subsets of a Set**
   - **Question:** Write a JavaScript function to generate all possible subsets of a given set of integers.
   - **Answer:**
     ```javascript
     function subsets(nums) {
       const result = [];

       function backtrack(start, current) {
         result.push([...current]);
         for (let i = start; i < nums.length; i++) {
           current.push(nums[i]);
           backtrack(i + 1, current);
           current.pop();
         }
       }

       backtrack(0, []);
       return result;
     }

     // Example usage
     console.log(subsets([1, 2, 3])); 
     // [[], [1], [1, 2], [1, 2, 3], [1, 3], [2], [2, 3], [3]]
     ```

#### 81. **Implement a Function to Check if Two Strings are Anagrams**
   - **Question:** Write a JavaScript function to determine if two strings are anagrams of each other.
   - **Answer:**
     ```javascript
     function areAnagrams(s1, s2) {
       if (s1.length !== s2.length) return false;

       const count = {};

       for (let char of s1) {
         count[char] = (count[char] || 0) + 1;
       }

       for (let char of s2) {
         if (!count[char]) return false;
         count[char]--;
       }

       return true;
     }

     // Example usage
     console.log(areAnagrams('listen', 'silent')); // true
     console.log(areAnagrams('hello', 'world')); // false
     ```

#### 82. **Implement a Function to Find the Longest Common Subsequence**
   - **Question:** Write a JavaScript function to find the longest common subsequence between two strings.
   - **Answer:**
     ```javascript
     function longestCommonSubsequence(text1, text2) {
       const dp = Array(text1.length + 1).fill(null).map(() => Array(text2.length + 1).fill(0));

       for (let i = 1; i <= text1.length; i++) {
         for (let j = 1; j <= text2.length; j++) {
           if (text1[i - 1] === text2[j - 1]) {
             dp[i][j] = dp[i - 1][j - 1] + 1;
           } else {
             dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
           }
         }
       }

       return dp[text1.length][text2.length];
     }

     // Example usage
     console.log(longestCommonSubsequence('abcde', 'ace')); // 3 ('ace')
     console.log(longestCommonSubsequence('abc', 'abc')); // 3 ('abc')
     ```

#### 83. **Implement a Function to Find the Longest Palindromic Substring**
   - **Question:** Write a JavaScript function to find the longest palindromic substring in a given string.
   - **Answer:**
     ```javascript
     function longestPalindrome(s) {
       let maxLength = 0;
       let start = 0;

       for (let i = 0; i < s.length; i++) {
         expandAroundCenter(i, i);   // Odd length palindromes
         expandAroundCenter(i, i + 1); // Even length palindromes
       }

       function expandAroundCenter(left, right) {
         while (left >= 0 && right < s.length && s[left] === s[right]) {
           left--;
           right++;
         }
         if (right - left - 1 > maxLength) {
           maxLength = right - left - 1;
           start = left + 1;
         }
       }

       return s.slice(start, start + maxLength);
     }

     // Example usage
     console.log(longestPalindrome('babad')); // 'bab' or 'aba'
     console.log(longestPalindrome('cbbd')); // 'bb'
     ```

#### 84. **Implement a Function to Validate a Binary Search Tree**
   - **Question:** Write a JavaScript function to determine if a given binary tree is a valid binary search tree.
   - **Answer:**
     ```javascript
     class TreeNode {
       constructor(val, left = null, right = null) {
         this.val = val;
         this.left = left;
         this.right = right;
       }
     }

     function isValidBST(root, min = null, max = null) {
       if (!root) return true;
       if (min !== null && root.val <= min) return false;
       if (max !== null && root.val >= max) return false;

       return isValidBST(root.left, min, root.val) && isValidBST(root.right, root.val, max);
     }

     // Example usage
     let tree = new TreeNode(2, new TreeNode(1), new TreeNode(3));
     console.log(isValidBST(tree)); // true

     tree = new TreeNode(5, new TreeNode(1), new TreeNode(4, new TreeNode(3), new TreeNode(6)));
     console.log(isValidBST(tree)); // false
     ```

#### 85. **Implement a Function to Perform Level-Order Traversal of a Binary Tree**
   - **Question:** Write a JavaScript function to perform a level-order traversal (breadth-first traversal) of a binary tree.
   - **Answer:**
     ```javascript
     class TreeNode {
       constructor(val, left = null, right = null) {
         this.val = val;
         this.left = left;
         this.right = right;
       }
     }

     function levelOrder(root) {
       const result = [];
       const queue = [root];

       while (queue.length > 0) {
         const levelSize = queue.length;
         const currentLevel = [];

         for (let i = 0; i < levelSize; i++) {
           const currentNode = queue.shift();
           if (currentNode) {
             currentLevel.push(currentNode.val);
             queue.push(currentNode.left);
             queue.push(currentNode.right);
           }
         }

         if (currentLevel.length > 0) {
           result.push(currentLevel);
         }
       }

       return result;
     }

     // Example usage
     let tree = new TreeNode(3, new TreeNode(9), new TreeNode(20, new TreeNode(15), new TreeNode(7)));
     console.log(levelOrder(tree)); // [[3], [9, 20], [15, 7]]
     ```

### JavaScript Coding Round Interview Questions and Answers

#### 86. **Implement a Function to Flatten a Nested Array (continued)**
   - **Question:** Write a JavaScript function to flatten a nested array into a single array.
   - **Answer:**
     ```javascript
     function flattenArray(arr) {
       const result = [];

       arr.forEach(element => {
         if (Array.isArray(element)) {
           result.push(...flattenArray(element));
         } else {
           result.push(element);
         }
       });

       return result;
     }

     // Example usage
     console.log(flattenArray([1, [2, [3, 4], [5]], 6])); // [1, 2, 3, 4, 5, 6]
     console.log(flattenArray([[1, 2, [3]], 4, [5, [6]]])); // [1, 2, 3, 4, 5, 6]
     ```

#### 87. **Implement a Function to Rotate an Array**
   - **Question:** Write a JavaScript function to rotate an array to the right by `k` steps.
   - **Answer:**
     ```javascript
     function rotateArray(nums, k) {
       k = k % nums.length;
       reverse(nums, 0, nums.length - 1);
       reverse(nums, 0, k - 1);
       reverse(nums, k, nums.length - 1);
     }

     function reverse(nums, start, end) {
       while (start < end) {
         [nums[start], nums[end]] = [nums[end], nums[start]];
         start++;
         end--;
       }
     }

     // Example usage
     const arr = [1, 2, 3, 4, 5, 6, 7];
     rotateArray(arr, 3);
     console.log(arr); // [5, 6, 7, 1, 2, 3, 4]
     ```

#### 88. **Implement a Function to Find the Maximum Subarray Sum**
   - **Question:** Write a JavaScript function to find the contiguous subarray within a one-dimensional array of numbers which has the largest sum.
   - **Answer:**
     ```javascript
     function maxSubArray(nums) {
       let maxSoFar = nums[0];
       let maxEndingHere = nums[0];

       for (let i = 1; i < nums.length; i++) {
         maxEndingHere = Math.max(nums[i], maxEndingHere + nums[i]);
         maxSoFar = Math.max(maxSoFar, maxEndingHere);
       }

       return maxSoFar;
     }

     // Example usage
     console.log(maxSubArray([-2, 1, -3, 4, -1, 2, 1, -5, 4])); // 6 (subarray [4, -1, 2, 1])
     console.log(maxSubArray([1])); // 1
     ```

#### 89. **Implement a Function to Find the First Non-Repeating Character in a String**
   - **Question:** Write a JavaScript function to find the first non-repeating character in a string and return its index. If it doesn't exist, return `-1`.
   - **Answer:**
     ```javascript
     function firstUniqChar(s) {
       const charCount = {};

       for (let char of s) {
         charCount[char] = (charCount[char] || 0) + 1;
       }

       for (let i = 0; i < s.length; i++) {
         if (charCount[s[i]] === 1) {
           return i;
         }
       }

       return -1;
     }

     // Example usage
     console.log(firstUniqChar("leetcode")); // 0
     console.log(firstUniqChar("loveleetcode")); // 2
     console.log(firstUniqChar("aabb")); // -1
     ```

#### 90. **Implement a Function to Generate All Permutations of a String**
   - **Question:** Write a JavaScript function to generate all permutations of a given string.
   - **Answer:**
     ```javascript
     function permute(str) {
       const result = [];

       if (str.length === 0) return [""];

       for (let i = 0; i < str.length; i++) {
         const currentChar = str[i];
         const remainingChars = str.slice(0, i) + str.slice(i + 1);
         const remainingPerms = permute(remainingChars);
         
         for (let perm of remainingPerms) {
           result.push(currentChar + perm);
         }
       }

       return result;
     }

     // Example usage
     console.log(permute("abc")); // ["abc", "acb", "bac", "bca", "cab", "cba"]
     ```

#### 91. **Implement a Function to Find the Longest Increasing Subsequence**
   - **Question:** Write a JavaScript function to find the length of the longest increasing subsequence in an array of numbers.
   - **Answer:**
     ```javascript
     function lengthOfLIS(nums) {
       if (nums.length === 0) return 0;

       const dp = Array(nums.length).fill(1);

       for (let i = 1; i < nums.length; i++) {
         for (let j = 0; j < i; j++) {
           if (nums[i] > nums[j]) {
             dp[i] = Math.max(dp[i], dp[j] + 1);
           }
         }
       }

       return Math.max(...dp);
     }

     // Example usage
     console.log(lengthOfLIS([10, 9, 2, 5, 3, 7, 101, 18])); // 4 (subsequence [2, 3, 7, 101])
     console.log(lengthOfLIS([0, 1, 0, 3, 2, 3])); // 4
     ```

#### 92. **Implement a Function to Check if a String is a Valid Parentheses String**
   - **Question:** Write a JavaScript function to check if a string containing only parentheses is valid. A string is valid if every opening parenthesis has a corresponding closing parenthesis and the pairs are properly nested.
   - **Answer:**
     ```javascript
     function isValidParentheses(s) {
       const stack = [];
       const map = {
         '(': ')',
         '{': '}',
         '[': ']'
       };

       for (let char of s) {
         if (map[char]) {
           stack.push(map[char]);
         } else if (stack.length === 0 || stack.pop() !== char) {
           return false;
         }
       }

       return stack.length === 0;
     }

     // Example usage
     console.log(isValidParentheses("()")); // true
     console.log(isValidParentheses("()[]{}")); // true
     console.log(isValidParentheses("(]")); // false
     ```

#### 93. **Implement a Function to Find the Missing Number in an Array**
   - **Question:** Write a JavaScript function to find the missing number from an array containing `n` distinct numbers in the range `[0, n]`.
   - **Answer:**
     ```javascript
     function missingNumber(nums) {
       let total = nums.length;
       for (let i = 0; i < nums.length; i++) {
         total += i - nums[i];
       }
       return total;
     }

     // Example usage
     console.log(missingNumber([3, 0, 1])); // 2
     console.log(missingNumber([9,6,4,2,3,5,7,0,1])); // 8
     ```

#### 94. **Implement a Function to Check if a Number is a Power of Two**
   - **Question:** Write a JavaScript function to determine if a given number is a power of two.
   - **Answer:**
     ```javascript
     function isPowerOfTwo(n) {
       if (n <= 0) return false;
       return (n & (n - 1)) === 0;
     }

     // Example usage
     console.log(isPowerOfTwo(1)); // true (2^0)
     console.log(isPowerOfTwo(16)); // true (2^4)
     console.log(isPowerOfTwo(218)); // false
     ```

#### 95. **Implement a Function to Reverse Words in a String**
   - **Question:** Write a JavaScript function to reverse the order of words in a given string.
   - **Answer:**
     ```javascript
     function reverseWords(s) {
       return s.trim().split(/\s+/).reverse().join(" ");
     }

     // Example usage
     console.log(reverseWords("the sky is blue")); // "blue is sky the"
     console.log(reverseWords("  hello world  ")); // "world hello"
     console.log(reverseWords("a good   example")); // "example good a"
     ```

### JavaScript Coding Round Interview Questions and Answers

#### 96. **Implement a Function to Find the Intersection of Two Arrays (continued)**
   - **Question:** Write a JavaScript function to find the intersection of two arrays, returning an array of the common elements.
   - **Answer:**
     ```javascript
     function intersect(nums1, nums2) {
       const map = {};
       const result = [];

       for (let num of nums1) {
         map[num] = (map[num] || 0) + 1;
       }

       for (let num of nums2) {
         if (map[num]) {
           result.push(num);
           map[num]--;
         }
       }

       return result;
     }

     // Example usage
     console.log(intersect([1, 2, 2, 1], [2, 2])); // [2, 2]
     console.log(intersect([4, 9, 5], [9, 4, 9, 8, 4])); // [4, 9]
     ```

#### 97. **Implement a Function to Convert a String to an Integer**
   - **Question:** Write a JavaScript function that converts a string to an integer (similar to the `atoi` function in C).
   - **Answer:**
     ```javascript
     function myAtoi(str) {
       str = str.trim();
       if (!str) return 0;

       let sign = 1;
       let i = 0;
       let result = 0;

       if (str[i] === '-' || str[i] === '+') {
         sign = str[i] === '-' ? -1 : 1;
         i++;
       }

       while (i < str.length && str[i] >= '0' && str[i] <= '9') {
         result = result * 10 + (str[i] - '0');
         if (result > 2147483647) {
           return sign === 1 ? 2147483647 : -2147483648;
         }
         i++;
       }

       return result * sign;
     }

     // Example usage
     console.log(myAtoi("42")); // 42
     console.log(myAtoi("   -42")); // -42
     console.log(myAtoi("4193 with words")); // 4193
     ```

#### 98. **Implement a Function to Group Anagrams**
   - **Question:** Write a JavaScript function that groups anagrams together from a list of strings.
   - **Answer:**
     ```javascript
     function groupAnagrams(strs) {
       const map = {};

       for (let str of strs) {
         const sorted = str.split('').sort().join('');
         if (!map[sorted]) {
           map[sorted] = [];
         }
         map[sorted].push(str);
       }

       return Object.values(map);
     }

     // Example usage
     console.log(groupAnagrams(["eat", "tea", "tan", "ate", "nat", "bat"]));
     // [["eat","tea","ate"],["tan","nat"],["bat"]]
     ```

#### 99. **Implement a Function to Calculate the Product of Array Except Self**
   - **Question:** Write a JavaScript function that returns an array where each element is the product of all the elements in the input array except itself.
   - **Answer:**
     ```javascript
     function productExceptSelf(nums) {
       const result = [];
       let product = 1;

       for (let i = 0; i < nums.length; i++) {
         result[i] = product;
         product *= nums[i];
       }

       product = 1;
       for (let i = nums.length - 1; i >= 0; i--) {
         result[i] *= product;
         product *= nums[i];
       }

       return result;
     }

     // Example usage
     console.log(productExceptSelf([1, 2, 3, 4])); // [24, 12, 8, 6]
     console.log(productExceptSelf([0, 1, 2, 3])); // [6, 0, 0, 0]
     ```

#### 100. **Implement a Function to Check if Two Strings are Isomorphic**
   - **Question:** Write a JavaScript function to determine if two strings are isomorphic. Two strings are isomorphic if the characters in one string can be replaced to get the other string.
   - **Answer:**
     ```javascript
     function isIsomorphic(s, t) {
       if (s.length !== t.length) return false;

       const mapS = {};
       const mapT = {};

       for (let i = 0; i < s.length; i++) {
         if (mapS[s[i]] !== mapT[t[i]]) return false;

         mapS[s[i]] = i + 1;
         mapT[t[i]] = i + 1;
       }

       return true;
     }

     // Example usage
     console.log(isIsomorphic("egg", "add")); // true
     console.log(isIsomorphic("foo", "bar")); // false
     console.log(isIsomorphic("paper", "title")); // true
     ```

#### 101. **Implement a Function to Find the Kth Largest Element in an Array**
   - **Question:** Write a JavaScript function to find the kth largest element in an unsorted array.
   - **Answer:**
     ```javascript
     function findKthLargest(nums, k) {
       nums.sort((a, b) => b - a);
       return nums[k - 1];
     }

     // Example usage
     console.log(findKthLargest([3, 2, 1, 5, 6, 4], 2)); // 5
     console.log(findKthLargest([3, 2, 3, 1, 2, 4, 5, 5, 6], 4)); // 4
     ```

#### 102. **Implement a Function to Merge Intervals**
   - **Question:** Write a JavaScript function to merge all overlapping intervals from a list of intervals.
   - **Answer:**
     ```javascript
     function mergeIntervals(intervals) {
       if (intervals.length === 0) return [];

       intervals.sort((a, b) => a[0] - b[0]);

       const merged = [intervals[0]];

       for (let i = 1; i < intervals.length; i++) {
         const last = merged[merged.length - 1];
         const current = intervals[i];

         if (current[0] <= last[1]) {
           last[1] = Math.max(last[1], current[1]);
         } else {
           merged.push(current);
         }
       }

       return merged;
     }

     // Example usage
     console.log(mergeIntervals([[1, 3], [2, 6], [8, 10], [15, 18]]));
     // [[1, 6], [8, 10], [15, 18]]
     console.log(mergeIntervals([[1, 4], [4, 5]]));
     // [[1, 5]]
     ```

#### 103. **Implement a Function to Calculate the Minimum Path Sum in a Grid**
   - **Question:** Write a JavaScript function to find a path from the top-left to the bottom-right corner of a grid, such that the sum of the numbers along the path is minimized.
   - **Answer:**
     ```javascript
     function minPathSum(grid) {
       const rows = grid.length;
       const cols = grid[0].length;

       for (let i = 1; i < rows; i++) {
         grid[i][0] += grid[i - 1][0];
       }

       for (let j = 1; j < cols; j++) {
         grid[0][j] += grid[0][j - 1];
       }

       for (let i = 1; i < rows; i++) {
         for (let j = 1; j < cols; j++) {
           grid[i][j] += Math.min(grid[i - 1][j], grid[i][j - 1]);
         }
       }

       return grid[rows - 1][cols - 1];
     }

     // Example usage
     console.log(minPathSum([
       [1, 3, 1],
       [1, 5, 1],
       [4, 2, 1]
     ])); // 7
     console.log(minPathSum([
       [1, 2, 3],
       [4, 5, 6]
     ])); // 12
     ```

#### 104. **Implement a Function to Find All Unique Subsets of an Array**
   - **Question:** Write a JavaScript function to return all possible unique subsets of an array.
   - **Answer:**
     ```javascript
     function subsets(nums) {
       const result = [[]];

       for (let num of nums) {
         const length = result.length;
         for (let i = 0; i < length; i++) {
           const subset = result[i].slice();
           subset.push(num);
           result.push(subset);
         }
       }

       return result;
     }

     // Example usage
     console.log(subsets([1, 2, 3]));
     // [[], [1], [2], [1,2], [3], [1,3], [2,3], [1,2,3]]
     ```

### JavaScript Coding Round Interview Questions and Answers

#### 105. **Implement a Function to Find the Longest Palindromic Substring**
   - **Question:** Write a JavaScript function that returns the longest palindromic substring in a given string.
   - **Answer:**
     ```javascript
     function longestPalindrome(s) {
       if (s.length < 2) return s;

       let start = 0, maxLength = 1;

       function expandAroundCenter(left, right) {
         while (left >= 0 && right < s.length && s[left] === s[right]) {
           left--;
           right++;
         }
         const length = right - left - 1;
         if (length > maxLength) {
           start = left + 1;
           maxLength = length;
         }
       }

       for (let i = 0; i < s.length; i++) {
         expandAroundCenter(i, i); // Odd length palindrome
         expandAroundCenter(i, i + 1); // Even length palindrome
       }

       return s.substring(start, start + maxLength);
     }

     // Example usage
     console.log(longestPalindrome("babad")); // "bab" or "aba"
     console.log(longestPalindrome("cbbd"));  // "bb"
     ```

#### 106. **Implement a Function to Check if a String is a Valid Palindrome**
   - **Question:** Write a JavaScript function to determine if a given string is a palindrome, considering only alphanumeric characters and ignoring cases.
   - **Answer:**
     ```javascript
     function isPalindrome(s) {
       s = s.replace(/[^A-Za-z0-9]/g, '').toLowerCase();
       let left = 0;
       let right = s.length - 1;

       while (left < right) {
         if (s[left] !== s[right]) return false;
         left++;
         right--;
       }

       return true;
     }

     // Example usage
     console.log(isPalindrome("A man, a plan, a canal: Panama")); // true
     console.log(isPalindrome("race a car")); // false
     ```

#### 107. **Implement a Function to Find All Permutations of a String**
   - **Question:** Write a JavaScript function that returns all permutations of a given string.
   - **Answer:**
     ```javascript
     function permute(str) {
       const result = [];

       function helper(path, used, remaining) {
         if (path.length === str.length) {
           result.push(path.join(''));
           return;
         }

         for (let i = 0; i < remaining.length; i++) {
           if (used[i]) continue;

           used[i] = true;
           path.push(remaining[i]);
           helper(path, used, remaining);
           path.pop();
           used[i] = false;
         }
       }

       helper([], Array(str.length).fill(false), str.split(''));
       return result;
     }

     // Example usage
     console.log(permute("abc"));
     // ["abc", "acb", "bac", "bca", "cab", "cba"]
     ```

#### 108. **Implement a Function to Check if Two Strings are Anagrams**
   - **Question:** Write a JavaScript function to determine if two strings are anagrams of each other.
   - **Answer:**
     ```javascript
     function isAnagram(s, t) {
       if (s.length !== t.length) return false;

       const count = {};

       for (let i = 0; i < s.length; i++) {
         count[s[i]] = (count[s[i]] || 0) + 1;
         count[t[i]] = (count[t[i]] || 0) - 1;
       }

       for (let key in count) {
         if (count[key] !== 0) return false;
       }

       return true;
     }

     // Example usage
     console.log(isAnagram("anagram", "nagaram")); // true
     console.log(isAnagram("rat", "car")); // false
     ```

#### 109. **Implement a Function to Rotate an Array**
   - **Question:** Write a JavaScript function that rotates an array to the right by `k` steps.
   - **Answer:**
     ```javascript
     function rotateArray(nums, k) {
       k = k % nums.length;
       reverse(nums, 0, nums.length - 1);
       reverse(nums, 0, k - 1);
       reverse(nums, k, nums.length - 1);
     }

     function reverse(arr, start, end) {
       while (start < end) {
         [arr[start], arr[end]] = [arr[end], arr[start]];
         start++;
         end--;
       }
     }

     // Example usage
     let arr = [1, 2, 3, 4, 5, 6, 7];
     rotateArray(arr, 3);
     console.log(arr); // [5, 6, 7, 1, 2, 3, 4]
     ```

#### 110. **Implement a Function to Find the Maximum Subarray Sum**
   - **Question:** Write a JavaScript function to find the contiguous subarray within a one-dimensional numeric array that has the largest sum.
   - **Answer:**
     ```javascript
     function maxSubArray(nums) {
       let maxSum = nums[0];
       let currentSum = nums[0];

       for (let i = 1; i < nums.length; i++) {
         currentSum = Math.max(nums[i], currentSum + nums[i]);
         maxSum = Math.max(maxSum, currentSum);
       }

       return maxSum;
     }

     // Example usage
     console.log(maxSubArray([-2,1,-3,4,-1,2,1,-5,4])); // 6
     console.log(maxSubArray([1])); // 1
     ```

#### 111. **Implement a Function to Find the Majority Element in an Array**
   - **Question:** Write a JavaScript function that finds the majority element in an array, where the majority element is the one that appears more than `n/2` times.
   - **Answer:**
     ```javascript
     function majorityElement(nums) {
       let count = 0;
       let candidate = null;

       for (let num of nums) {
         if (count === 0) {
           candidate = num;
         }
         count += (num === candidate) ? 1 : -1;
       }

       return candidate;
     }

     // Example usage
     console.log(majorityElement([3,2,3])); // 3
     console.log(majorityElement([2,2,1,1,1,2,2])); // 2
     ```

#### 112. **Implement a Function to Remove Duplicates from a Sorted Array**
   - **Question:** Write a JavaScript function that removes duplicates in-place from a sorted array, returning the new length of the array.
   - **Answer:**
     ```javascript
     function removeDuplicates(nums) {
       if (nums.length === 0) return 0;

       let i = 0;
       for (let j = 1; j < nums.length; j++) {
         if (nums[j] !== nums[i]) {
           i++;
           nums[i] = nums[j];
         }
       }

       return i + 1;
     }

     // Example usage
     let arr = [1, 1, 2];
     console.log(removeDuplicates(arr)); // 2
     console.log(arr); // [1, 2, 2]
     ```

#### 113. **Implement a Function to Check if a Number is a Happy Number**
   - **Question:** Write a JavaScript function that determines if a number is a happy number. A happy number is defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1, or it loops endlessly in a cycle that does not include 1.
   - **Answer:**
     ```javascript
     function isHappy(n) {
       let slow = n, fast = n;

       do {
         slow = sumOfSquares(slow);
         fast = sumOfSquares(sumOfSquares(fast));
       } while (slow !== fast);

       return slow === 1;
     }

     function sumOfSquares(num) {
       let sum = 0;
       while (num > 0) {
         let digit = num % 10;
         sum += digit * digit;
         num = Math.floor(num / 10);
       }
       return sum;
     }

     // Example usage
     console.log(isHappy(19)); // true
     console.log(isHappy(2)); // false
     ```

### JavaScript Coding Round Interview Questions and Answers

#### 114. **Implement a Function to Check if a Binary Tree is Symmetric**
   - **Question:** Write a JavaScript function that checks if a binary tree is symmetric around its center.
   - **Answer:**
     ```javascript
     function isSymmetric(root) {
       if (!root) return true;

       function isMirror(t1, t2) {
         if (!t1 && !t2) return true;
         if (!t1 || !t2) return false;
         return (t1.val === t2.val) &&
                isMirror(t1.right, t2.left) &&
                isMirror(t1.left, t2.right);
       }

       return isMirror(root.left, root.right);
     }

     // Example usage
     const tree = {
       val: 1,
       left: {
         val: 2,
         left: { val: 3, left: null, right: null },
         right: { val: 4, left: null, right: null }
       },
       right: {
         val: 2,
         left: { val: 4, left: null, right: null },
         right: { val: 3, left: null, right: null }
       }
     };
     console.log(isSymmetric(tree)); // true
     ```

#### 115. **Implement a Function to Flatten a Nested Array**
   - **Question:** Write a JavaScript function that flattens a nested array structure into a single array.
   - **Answer:**
     ```javascript
     function flattenArray(arr) {
       return arr.reduce((flat, toFlatten) => {
         return flat.concat(Array.isArray(toFlatten) ? flattenArray(toFlatten) : toFlatten);
       }, []);
     }

     // Example usage
     console.log(flattenArray([1, [2, [3, [4]], 5]])); // [1, 2, 3, 4, 5]
     ```

#### 116. **Implement a Function to Calculate the Product of an Array Except Self**
   - **Question:** Write a JavaScript function that returns an array output such that `output[i]` is equal to the product of all the elements of the input array except `nums[i]`.
   - **Answer:**
     ```javascript
     function productExceptSelf(nums) {
       const result = new Array(nums.length).fill(1);

       let leftProduct = 1;
       for (let i = 0; i < nums.length; i++) {
         result[i] *= leftProduct;
         leftProduct *= nums[i];
       }

       let rightProduct = 1;
       for (let i = nums.length - 1; i >= 0; i--) {
         result[i] *= rightProduct;
         rightProduct *= nums[i];
       }

       return result;
     }

     // Example usage
     console.log(productExceptSelf([1, 2, 3, 4])); // [24, 12, 8, 6]
     ```

#### 117. **Implement a Function to Merge Two Sorted Arrays**
   - **Question:** Write a JavaScript function that merges two sorted arrays into a single sorted array.
   - **Answer:**
     ```javascript
     function mergeSortedArrays(arr1, arr2) {
       const result = [];
       let i = 0, j = 0;

       while (i < arr1.length && j < arr2.length) {
         if (arr1[i] < arr2[j]) {
           result.push(arr1[i]);
           i++;
         } else {
           result.push(arr2[j]);
           j++;
         }
       }

       return result.concat(arr1.slice(i)).concat(arr2.slice(j));
     }

     // Example usage
     console.log(mergeSortedArrays([1, 3, 5], [2, 4, 6])); // [1, 2, 3, 4, 5, 6]
     ```

#### 118. **Implement a Function to Find the Intersection of Two Arrays**
   - **Question:** Write a JavaScript function that returns the intersection of two arrays.
   - **Answer:**
     ```javascript
     function arrayIntersection(arr1, arr2) {
       const set1 = new Set(arr1);
       const set2 = new Set(arr2);
       const intersection = [];

       set2.forEach(item => {
         if (set1.has(item)) {
           intersection.push(item);
         }
       });

       return intersection;
     }

     // Example usage
     console.log(arrayIntersection([1, 2, 2, 1], [2, 2])); // [2]
     console.log(arrayIntersection([4, 9, 5], [9, 4, 9, 8, 4])); // [9, 4]
     ```

#### 119. **Implement a Function to Generate Pascal's Triangle**
   - **Question:** Write a JavaScript function that generates Pascal's Triangle up to `n` rows.
   - **Answer:**
     ```javascript
     function generatePascalsTriangle(numRows) {
       const triangle = [];

       for (let i = 0; i < numRows; i++) {
         triangle[i] = [];
         triangle[i][0] = triangle[i][i] = 1;

         for (let j = 1; j < i; j++) {
           triangle[i][j] = triangle[i - 1][j - 1] + triangle[i - 1][j];
         }
       }

       return triangle;
     }

     // Example usage
     console.log(generatePascalsTriangle(5));
     /*
     [
       [1],
       [1, 1],
       [1, 2, 1],
       [1, 3, 3, 1],
       [1, 4, 6, 4, 1]
     ]
     */
     ```

#### 120. **Implement a Function to Perform Binary Search**
   - **Question:** Write a JavaScript function that performs a binary search on a sorted array to find the index of a given target value.
   - **Answer:**
     ```javascript
     function binarySearch(arr, target) {
       let left = 0;
       let right = arr.length - 1;

       while (left <= right) {
         const mid = Math.floor((left + right) / 2);

         if (arr[mid] === target) return mid;

         if (arr[mid] < target) {
           left = mid + 1;
         } else {
           right = mid - 1;
         }
       }

       return -1;
     }

     // Example usage
     console.log(binarySearch([1, 2, 3, 4, 5, 6, 7, 8, 9], 5)); // 4
     console.log(binarySearch([1, 2, 3, 4, 5, 6, 7, 8, 9], 10)); // -1
     ```

#### 121. **Implement a Function to Convert Roman Numerals to Integers**
   - **Question:** Write a JavaScript function that converts a Roman numeral string to an integer.
   - **Answer:**
     ```javascript
     function romanToInt(s) {
       const romanMap = {
         'I': 1,
         'V': 5,
         'X': 10,
         'L': 50,
         'C': 100,
         'D': 500,
         'M': 1000
       };

       let total = 0;
       let prevValue = 0;

       for (let i = s.length - 1; i >= 0; i--) {
         const currentValue = romanMap[s[i]];

         if (currentValue < prevValue) {
           total -= currentValue;
         } else {
           total += currentValue;
         }

         prevValue = currentValue;
       }

       return total;
     }

     // Example usage
     console.log(romanToInt("III")); // 3
     console.log(romanToInt("IX")); // 9
     console.log(romanToInt("LVIII")); // 58
     console.log(romanToInt("MCMXCIV")); // 1994
     ```

#### 122. **Implement a Function to Convert Integers to Roman Numerals**
   - **Question:** Write a JavaScript function that converts an integer to a Roman numeral string.
   - **Answer:**
     ```javascript
     function intToRoman(num) {
       const values = [
         1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1
       ];
       const symbols = [
         "M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"
       ];

       let roman = '';

       for (let i = 0; i < values.length && num > 0; i++) {
         while (num >= values[i]) {
           num -= values[i];
           roman += symbols[i];
         }
       }

       return roman;
     }

     // Example usage
     console.log(intToRoman(3)); // "III"
     console.log(intToRoman(9)); // "IX"
     console.log(intToRoman(58)); // "LVIII"
     console.log(intToRoman(1994)); // "MCMXCIV"
     ```

### JavaScript Coding Round Interview Questions and Answers

#### 123. **Implement a Function to Rotate an Array**
   - **Question:** Write a JavaScript function that rotates an array to the right by a given number of steps.
   - **Answer:**
     ```javascript
     function rotateArray(nums, k) {
       k = k % nums.length;
       reverse(nums, 0, nums.length - 1);
       reverse(nums, 0, k - 1);
       reverse(nums, k, nums.length - 1);
     }

     function reverse(nums, start, end) {
       while (start < end) {
         let temp = nums[start];
         nums[start] = nums[end];
         nums[end] = temp;
         start++;
         end--;
       }
     }

     // Example usage
     let arr = [1, 2, 3, 4, 5, 6, 7];
     rotateArray(arr, 3);
     console.log(arr); // [5, 6, 7, 1, 2, 3, 4]
     ```

#### 124. **Implement a Function to Find the First Unique Character in a String**
   - **Question:** Write a JavaScript function that finds the first non-repeating character in a string and returns its index. If it doesn't exist, return -1.
   - **Answer:**
     ```javascript
     function firstUniqChar(s) {
       const charCount = {};

       for (let i = 0; i < s.length; i++) {
         charCount[s[i]] = (charCount[s[i]] || 0) + 1;
       }

       for (let i = 0; i < s.length; i++) {
         if (charCount[s[i]] === 1) {
           return i;
         }
       }

       return -1;
     }

     // Example usage
     console.log(firstUniqChar("leetcode")); // 0
     console.log(firstUniqChar("loveleetcode")); // 2
     console.log(firstUniqChar("aabb")); // -1
     ```

#### 125. **Implement a Function to Group Anagrams**
   - **Question:** Write a JavaScript function that groups anagrams from a list of strings.
   - **Answer:**
     ```javascript
     function groupAnagrams(strs) {
       const map = new Map();

       for (let str of strs) {
         let sortedStr = str.split('').sort().join('');
         if (!map.has(sortedStr)) {
           map.set(sortedStr, []);
         }
         map.get(sortedStr).push(str);
       }

       return Array.from(map.values());
     }

     // Example usage
     console.log(groupAnagrams(["eat", "tea", "tan", "ate", "nat", "bat"]));
     // [["eat","tea","ate"],["tan","nat"],["bat"]]
     ```

#### 126. **Implement a Function to Check if a Linked List has a Cycle**
   - **Question:** Write a JavaScript function to detect if a singly linked list has a cycle in it.
   - **Answer:**
     ```javascript
     function hasCycle(head) {
       let slow = head;
       let fast = head;

       while (fast !== null && fast.next !== null) {
         slow = slow.next;
         fast = fast.next.next;
         if (slow === fast) {
           return true;
         }
       }

       return false;
     }

     // Example usage
     const list = {
       val: 3,
       next: {
         val: 2,
         next: {
           val: 0,
           next: {
             val: -4,
             next: null // Change this to point to list.next for a cycle
           }
         }
       }
     };
     console.log(hasCycle(list)); // false (for this specific example without a cycle)
     ```

#### 127. **Implement a Function to Find the Longest Palindromic Substring**
   - **Question:** Write a JavaScript function to find the longest palindromic substring in a given string.
   - **Answer:**
     ```javascript
     function longestPalindrome(s) {
       if (s.length < 2) return s;

       let start = 0, maxLength = 1;

       function expandAroundCenter(left, right) {
         while (left >= 0 && right < s.length && s[left] === s[right]) {
           if (right - left + 1 > maxLength) {
             start = left;
             maxLength = right - left + 1;
           }
           left--;
           right++;
         }
       }

       for (let i = 0; i < s.length; i++) {
         expandAroundCenter(i, i); // Odd length
         expandAroundCenter(i, i + 1); // Even length
       }

       return s.substring(start, start + maxLength);
     }

     // Example usage
     console.log(longestPalindrome("babad")); // "bab" or "aba"
     console.log(longestPalindrome("cbbd")); // "bb"
     ```

#### 128. **Implement a Function to Calculate the Maximum Subarray Sum**
   - **Question:** Write a JavaScript function to find the contiguous subarray within an array (containing at least one number) that has the largest sum.
   - **Answer:**
     ```javascript
     function maxSubArray(nums) {
       let maxSoFar = nums[0];
       let maxEndingHere = nums[0];

       for (let i = 1; i < nums.length; i++) {
         maxEndingHere = Math.max(nums[i], maxEndingHere + nums[i]);
         maxSoFar = Math.max(maxSoFar, maxEndingHere);
       }

       return maxSoFar;
     }

     // Example usage
     console.log(maxSubArray([-2,1,-3,4,-1,2,1,-5,4])); // 6 ([4,-1,2,1])
     console.log(maxSubArray([1])); // 1
     console.log(maxSubArray([5,4,-1,7,8])); // 23
     ```

#### 129. **Implement a Function to Find the Kth Largest Element in an Array**
   - **Question:** Write a JavaScript function to find the kth largest element in an unsorted array. Note that it is the kth largest element in sorted order, not the kth distinct element.
   - **Answer:**
     ```javascript
     function findKthLargest(nums, k) {
       nums.sort((a, b) => b - a);
       return nums[k - 1];
     }

     // Example usage
     console.log(findKthLargest([3,2,1,5,6,4], 2)); // 5
     console.log(findKthLargest([3,2,3,1,2,4,5,5,6], 4)); // 4
     ```

#### 130. **Implement a Function to Calculate the Trapping Rain Water**
   - **Question:** Write a JavaScript function to calculate how much water it is able to trap after raining given an array representing an elevation map.
   - **Answer:**
     ```javascript
     function trap(height) {
       let left = 0, right = height.length - 1;
       let leftMax = 0, rightMax = 0;
       let water = 0;

       while (left < right) {
         if (height[left] < height[right]) {
           if (height[left] >= leftMax) {
             leftMax = height[left];
           } else {
             water += leftMax - height[left];
           }
           left++;
         } else {
           if (height[right] >= rightMax) {
             rightMax = height[right];
           } else {
             water += rightMax - height[right];
           }
           right--;
         }
       }

       return water;
     }

     // Example usage
     console.log(trap([0,1,0,2,1,0,1,3,2,1,2,1])); // 6
     console.log(trap([4,2,0,3,2,5])); // 9
     ```

#### 131. **Implement a Function to Check for Valid Parentheses**
   - **Question:** Write a JavaScript function to determine if the input string has valid parentheses. The input string can contain the characters `(`, `)`, `{`, `}`, `[` and `]`.
   - **Answer:**
     ```javascript
     function isValid(s) {
       const stack = [];
       const map = {
         '(': ')',
         '{': '}',
         '[': ']'
       };

       for (let char of s) {
         if (map[char]) {
           stack.push(map[char]);
         } else if (stack.length > 0 && stack[stack.length - 1] === char) {
           stack.pop();
         } else {
           return false;
         }
       }

       return stack.length === 0;
     }

     // Example usage
     console.log(isValid("()")); // true
     console.log(isValid("()[]{}")); // true
     console.log(isValid("(]")); // false
     console.log(isValid("([)]")); // false
     console.log(isValid("{[]}")); // true
     ```

### JavaScript Coding Round Interview Questions and Answers

#### 132. **Implement a Function to Find the Minimum Path Sum in a Grid**
   - **Question:** Write a JavaScript function to find a path from the top-left to the bottom-right of a grid that minimizes the sum of all numbers along its path. You can only move either down or right at any point in time.
   - **Answer:**
     ```javascript
     function minPathSum(grid) {
       let rows = grid.length;
       let cols = grid[0].length;

       for (let i = 1; i < rows; i++) {
         grid[i][0] += grid[i - 1][0];
       }

       for (let j = 1; j < cols; j++) {
         grid[0][j] += grid[0][j - 1];
       }

       for (let i = 1; i < rows; i++) {
         for (let j = 1; j < cols; j++) {
           grid[i][j] += Math.min(grid[i - 1][j], grid[i][j - 1]);
         }
       }

       return grid[rows - 1][cols - 1];
     }

     // Example usage
     let grid = [
       [1, 3, 1],
       [1, 5, 1],
       [4, 2, 1]
     ];
     console.log(minPathSum(grid)); // 7
     ```

#### 133. **Implement a Function to Calculate the Product of Array Except Self**
   - **Question:** Write a JavaScript function that takes an array of integers `nums`, and returns an array `output` such that `output[i]` is equal to the product of all the elements of `nums` except `nums[i]`. Solve it without using division and in O(n) time.
   - **Answer:**
     ```javascript
     function productExceptSelf(nums) {
       let n = nums.length;
       let output = new Array(n).fill(1);

       let leftProduct = 1;
       for (let i = 0; i < n; i++) {
         output[i] = leftProduct;
         leftProduct *= nums[i];
       }

       let rightProduct = 1;
       for (let i = n - 1; i >= 0; i--) {
         output[i] *= rightProduct;
         rightProduct *= nums[i];
       }

       return output;
     }

     // Example usage
     console.log(productExceptSelf([1,2,3,4])); // [24, 12, 8, 6]
     ```

#### 134. **Implement a Function to Find All Possible Subsets (The Power Set)**
   - **Question:** Write a JavaScript function that takes an array of distinct integers and returns all possible subsets (the power set).
   - **Answer:**
     ```javascript
     function subsets(nums) {
       const res = [];

       function backtrack(start, path) {
         res.push([...path]);
         for (let i = start; i < nums.length; i++) {
           path.push(nums[i]);
           backtrack(i + 1, path);
           path.pop();
         }
       }

       backtrack(0, []);
       return res;
     }

     // Example usage
     console.log(subsets([1,2,3]));
     // Output: [[],[1],[1,2],[1,2,3],[1,3],[2],[2,3],[3]]
     ```

#### 135. **Implement a Function to Find the Number of Islands**
   - **Question:** Write a JavaScript function to find the number of islands in a grid. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically.
   - **Answer:**
     ```javascript
     function numIslands(grid) {
       if (grid.length === 0) return 0;
       let count = 0;

       function dfs(i, j) {
         if (i < 0 || i >= grid.length || j < 0 || j >= grid[0].length || grid[i][j] === '0') {
           return;
         }
         grid[i][j] = '0';
         dfs(i + 1, j);
         dfs(i - 1, j);
         dfs(i, j + 1);
         dfs(i, j - 1);
       }

       for (let i = 0; i < grid.length; i++) {
         for (let j = 0; j < grid[0].length; j++) {
           if (grid[i][j] === '1') {
             count++;
             dfs(i, j);
           }
         }
       }

       return count;
     }

     // Example usage
     let grid = [
       ['1', '1', '0', '0', '0'],
       ['1', '1', '0', '0', '0'],
       ['0', '0', '1', '0', '0'],
       ['0', '0', '0', '1', '1']
     ];
     console.log(numIslands(grid)); // 3
     ```

#### 136. **Implement a Function to Merge Intervals**
   - **Question:** Write a JavaScript function to merge overlapping intervals.
   - **Answer:**
     ```javascript
     function merge(intervals) {
       if (intervals.length <= 1) return intervals;

       intervals.sort((a, b) => a[0] - b[0]);

       const result = [];
       let [start, end] = intervals[0];

       for (let i = 1; i < intervals.length; i++) {
         const [currentStart, currentEnd] = intervals[i];

         if (currentStart <= end) {
           end = Math.max(end, currentEnd);
         } else {
           result.push([start, end]);
           [start, end] = intervals[i];
         }
       }

       result.push([start, end]);
       return result;
     }

     // Example usage
     console.log(merge([[1,3],[2,6],[8,10],[15,18]]));
     // Output: [[1,6],[8,10],[15,18]]
     ```

#### 137. **Implement a Function to Generate Permutations**
   - **Question:** Write a JavaScript function that returns all possible permutations of an array of distinct integers.
   - **Answer:**
     ```javascript
     function permute(nums) {
       const res = [];

       function backtrack(path, options) {
         if (path.length === nums.length) {
           res.push([...path]);
           return;
         }
         for (let i = 0; i < options.length; i++) {
           path.push(options[i]);
           backtrack(path, options.filter((_, index) => index !== i));
           path.pop();
         }
       }

       backtrack([], nums);
       return res;
     }

     // Example usage
     console.log(permute([1,2,3]));
     // Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
     ```

#### 138. **Implement a Function to Perform Binary Search**
   - **Question:** Write a JavaScript function that performs binary search on a sorted array and returns the index of the target element, or -1 if it is not found.
   - **Answer:**
     ```javascript
     function binarySearch(nums, target) {
       let left = 0;
       let right = nums.length - 1;

       while (left <= right) {
         const mid = Math.floor((left + right) / 2);
         if (nums[mid] === target) {
           return mid;
         } else if (nums[mid] < target) {
           left = mid + 1;
         } else {
           right = mid - 1;
         }
       }

       return -1;
     }

     // Example usage
     console.log(binarySearch([1, 2, 3, 4, 5, 6, 7], 4)); // 3
     console.log(binarySearch([1, 2, 3, 4, 5, 6, 7], 9)); // -1
     ```

#### 139. **Implement a Function to Convert Roman Numerals to Integers**
   - **Question:** Write a JavaScript function that converts a Roman numeral to an integer.
   - **Answer:**
     ```javascript
     function romanToInt(s) {
       const map = {
         'I': 1,
         'V': 5,
         'X': 10,
         'L': 50,
         'C': 100,
         'D': 500,
         'M': 1000
       };
       let result = 0;

       for (let i = 0; i < s.length; i++) {
         const current = map[s[i]];
         const next = map[s[i + 1]];

         if (current < next) {
           result -= current;
         } else {
           result += current;
         }
       }

       return result;
     }

     // Example usage
     console.log(romanToInt("III")); // 3
     console.log(romanToInt("IV")); // 4
     console.log(romanToInt("IX")); // 9
     console.log(romanToInt("LVIII")); // 58
     console.log(romanToInt("MCMXCIV")); // 1994
     ```

### JavaScript Coding Round Interview Questions and Answers

#### 140. **Implement a Function to Check if a Linked List is Palindrome**
   - **Question:** Write a JavaScript function to check whether a singly linked list is a palindrome.
   - **Answer:**
     ```javascript
     function isPalindrome(head) {
       let slow = head;
       let fast = head;
       let prev, temp;

       // Find the middle of the linked list
       while (fast && fast.next) {
         fast = fast.next.next;
         temp = slow.next;
         slow.next = prev;
         prev = slow;
         slow = temp;
       }

       // For odd-sized lists, skip the middle element
       if (fast) slow = slow.next;

       // Compare the two halves
       while (slow) {
         if (slow.val !== prev.val) return false;
         slow = slow.next;
         prev = prev.next;
       }

       return true;
     }

     // Example usage
     function ListNode(val, next = null) {
       this.val = val;
       this.next = next;
     }

     let head = new ListNode(1, new ListNode(2, new ListNode(2, new ListNode(1))));
     console.log(isPalindrome(head)); // true
     ```

#### 141. **Implement a Function to Rotate an Array**
   - **Question:** Write a JavaScript function to rotate an array to the right by `k` steps, where `k` is non-negative.
   - **Answer:**
     ```javascript
     function rotate(nums, k) {
       k = k % nums.length;
       reverse(nums, 0, nums.length - 1);
       reverse(nums, 0, k - 1);
       reverse(nums, k, nums.length - 1);
     }

     function reverse(nums, start, end) {
       while (start < end) {
         let temp = nums[start];
         nums[start] = nums[end];
         nums[end] = temp;
         start++;
         end--;
       }
     }

     // Example usage
     let arr = [1, 2, 3, 4, 5, 6, 7];
     rotate(arr, 3);
     console.log(arr); // [5, 6, 7, 1, 2, 3, 4]
     ```

#### 142. **Implement a Function to Find the Longest Palindromic Substring**
   - **Question:** Write a JavaScript function that finds the longest palindromic substring in a given string.
   - **Answer:**
     ```javascript
     function longestPalindrome(s) {
       if (s.length === 0) return "";

       let start = 0;
       let end = 0;

       for (let i = 0; i < s.length; i++) {
         let len1 = expandAroundCenter(s, i, i);
         let len2 = expandAroundCenter(s, i, i + 1);
         let len = Math.max(len1, len2);

         if (len > end - start) {
           start = i - Math.floor((len - 1) / 2);
           end = i + Math.floor(len / 2);
         }
       }

       return s.substring(start, end + 1);
     }

     function expandAroundCenter(s, left, right) {
       while (left >= 0 && right < s.length && s[left] === s[right]) {
         left--;
         right++;
       }
       return right - left - 1;
     }

     // Example usage
     console.log(longestPalindrome("babad")); // "bab" or "aba"
     console.log(longestPalindrome("cbbd")); // "bb"
     ```

#### 143. **Implement a Function to Reverse Nodes in k-Group**
   - **Question:** Write a JavaScript function to reverse the nodes of a linked list `k` at a time and return its modified list. `k` is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of `k` then left-out nodes in the end should remain as it is.
   - **Answer:**
     ```javascript
     function reverseKGroup(head, k) {
       if (!head || k === 1) return head;

       let dummy = new ListNode(0);
       dummy.next = head;

       let curr = dummy, prev = dummy, next = dummy;
       let count = 0;
       while (curr.next) {
         curr = curr.next;
         count++;
       }

       while (count >= k) {
         curr = prev.next;
         next = curr.next;
         for (let i = 1; i < k; i++) {
           curr.next = next.next;
           next.next = prev.next;
           prev.next = next;
           next = curr.next;
         }
         prev = curr;
         count -= k;
       }
       return dummy.next;
     }

     // Example usage
     function ListNode(val, next = null) {
       this.val = val;
       this.next = next;
     }

     let head = new ListNode(1, new ListNode(2, new ListNode(3, new ListNode(4, new ListNode(5)))));
     let result = reverseKGroup(head, 2);
     while (result) {
       console.log(result.val); // 2 -> 1 -> 4 -> 3 -> 5
       result = result.next;
     }
     ```

#### 144. **Implement a Function to Validate a Binary Search Tree**
   - **Question:** Write a JavaScript function to validate if a given binary tree is a binary search tree (BST).
   - **Answer:**
     ```javascript
     function isValidBST(root, min = null, max = null) {
       if (!root) return true;

       if ((min !== null && root.val <= min) || (max !== null && root.val >= max)) {
         return false;
       }

       return isValidBST(root.left, min, root.val) && isValidBST(root.right, root.val, max);
     }

     // Example usage
     function TreeNode(val, left = null, right = null) {
       this.val = val;
       this.left = left;
       this.right = right;
     }

     let root = new TreeNode(2, new TreeNode(1), new TreeNode(3));
     console.log(isValidBST(root)); // true

     root = new TreeNode(5, new TreeNode(1), new TreeNode(4, new TreeNode(3), new TreeNode(6)));
     console.log(isValidBST(root)); // false
     ```

#### 145. **Implement a Function to Find the Longest Common Prefix**
   - **Question:** Write a JavaScript function that finds the longest common prefix string amongst an array of strings. If there is no common prefix, return an empty string.
   - **Answer:**
     ```javascript
     function longestCommonPrefix(strs) {
       if (!strs.length) return "";

       let prefix = strs[0];
       for (let i = 1; i < strs.length; i++) {
         while (strs[i].indexOf(prefix) !== 0) {
           prefix = prefix.substring(0, prefix.length - 1);
           if (!prefix) return "";
         }
       }

       return prefix;
     }

     // Example usage
     console.log(longestCommonPrefix(["flower","flow","flight"])); // "fl"
     console.log(longestCommonPrefix(["dog","racecar","car"])); // ""
     ```

#### 146. **Implement a Function to Find the First Missing Positive**
   - **Question:** Write a JavaScript function to find the smallest missing positive integer from an unsorted integer array.
   - **Answer:**
     ```javascript
     function firstMissingPositive(nums) {
       let n = nums.length;

       for (let i = 0; i < n; i++) {
         while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] !== nums[i]) {
           [nums[nums[i] - 1], nums[i]] = [nums[i], nums[nums[i] - 1]];
         }
       }

       for (let i = 0; i < n; i++) {
         if (nums[i] !== i + 1) return i + 1;
       }

       return n + 1;
     }

     // Example usage
     console.log(firstMissingPositive([1,2,0])); // 3
     console.log(firstMissingPositive([3,4,-1,1])); // 2
     console.log(firstMissingPositive([7,8,9,11,12])); // 1
     ```

### JavaScript Coding Round Interview Questions and Answers

#### 147. **Complete the Function to Deserialize a Binary Tree (Continued from 146)**
   - **Question:** Continue writing the function to deserialize a binary tree from where it left off in question 146.
   - **Answer:**
     ```javascript
     function deserialize(data) {
       const vals = data.split(",");
       let i = 0;

       function dfs() {
         if (vals[i] === "null") {
           i++;
           return null;
         }
         let node = new TreeNode(parseInt(vals[i]));
         i++;
         node.left = dfs();
         node.right = dfs();
         return node;
       }

       return dfs();
     }

     // Example usage
     function TreeNode(val, left = null, right = null) {
       this.val = val;
       this.left = left;
       this.right = right;
     }

     let root = new TreeNode(1, new TreeNode(2), new TreeNode(3, new TreeNode(4), new TreeNode(5)));
     let serialized = serialize(root);
     console.log(serialized); // "1,2,null,null,3,4,null,null,5,null,null"

     let deserialized = deserialize(serialized);
     console.log(deserialized); // Returns the root node of the reconstructed binary tree
     ```

#### 148. **Implement a Function to Flatten a Binary Tree to a Linked List**
   - **Question:** Write a JavaScript function to flatten a binary tree into a linked list in-place. The linked list should use the right pointers of the tree nodes.
   - **Answer:**
     ```javascript
     function flatten(root) {
       if (!root) return;

       let stack = [root];
       let prev = null;

       while (stack.length) {
         let curr = stack.pop();

         if (prev) {
           prev.right = curr;
           prev.left = null;
         }

         if (curr.right) stack.push(curr.right);
         if (curr.left) stack.push(curr.left);

         prev = curr;
       }
     }

     // Example usage
     function TreeNode(val, left = null, right = null) {
       this.val = val;
       this.left = left;
       this.right = right;
     }

     let root = new TreeNode(1, new TreeNode(2, new TreeNode(3), new TreeNode(4)), new TreeNode(5, null, new TreeNode(6)));
     flatten(root);
     while (root) {
       console.log(root.val); // 1 -> 2 -> 3 -> 4 -> 5 -> 6
       root = root.right;
     }
     ```

#### 149. **Implement a Function to Find All Anagrams of a String in Another String**
   - **Question:** Write a JavaScript function to find all start indices of `p`'s anagrams in `s`.
   - **Answer:**
     ```javascript
     function findAnagrams(s, p) {
       let result = [];
       let pCount = new Array(26).fill(0);
       let sCount = new Array(26).fill(0);

       for (let char of p) {
         pCount[char.charCodeAt(0) - "a".charCodeAt(0)]++;
       }

       for (let i = 0; i < s.length; i++) {
         sCount[s[i].charCodeAt(0) - "a".charCodeAt(0)]++;

         if (i >= p.length) {
           sCount[s[i - p.length].charCodeAt(0) - "a".charCodeAt(0)]--;
         }

         if (sCount.join("") === pCount.join("")) {
           result.push(i - p.length + 1);
         }
       }

       return result;
     }

     // Example usage
     console.log(findAnagrams("cbaebabacd", "abc")); // [0, 6]
     console.log(findAnagrams("abab", "ab")); // [0, 1, 2]
     ```

#### 150. **Implement a Function to Find the Minimum Path Sum in a Grid**
   - **Question:** Write a JavaScript function that finds the minimum path sum from the top left to the bottom right of a given grid. You can only move down or right at any point in time.
   - **Answer:**
     ```javascript
     function minPathSum(grid) {
       let m = grid.length;
       let n = grid[0].length;

       for (let i = 1; i < m; i++) {
         grid[i][0] += grid[i - 1][0];
       }

       for (let j = 1; j < n; j++) {
         grid[0][j] += grid[0][j - 1];
       }

       for (let i = 1; i < m; i++) {
         for (let j = 1; j < n; j++) {
           grid[i][j] += Math.min(grid[i - 1][j], grid[i][j - 1]);
         }
       }

       return grid[m - 1][n - 1];
     }

     // Example usage
     console.log(minPathSum([[1,3,1],[1,5,1],[4,2,1]])); // 7
     console.log(minPathSum([[1,2,3],[4,5,6]])); // 12
     ```

#### 151. **Implement a Function to Detect a Cycle in a Linked List**
   - **Question:** Write a JavaScript function to detect if a linked list has a cycle in it.
   - **Answer:**
     ```javascript
     function hasCycle(head) {
       let slow = head;
       let fast = head;

       while (fast && fast.next) {
         slow = slow.next;
         fast = fast.next.next;

         if (slow === fast) return true;
       }

       return false;
     }

     // Example usage
     function ListNode(val, next = null) {
       this.val = val;
       this.next = next;
     }

     let head = new ListNode(3, new ListNode(2, new ListNode(0, new ListNode(-4))));
     head.next.next.next.next = head.next; // Creates a cycle
     console.log(hasCycle(head)); // true
     ```

#### 152. **Implement a Function to Find the Maximum Product Subarray**
   - **Question:** Write a JavaScript function to find the contiguous subarray within an array (containing at least one number) which has the largest product.
   - **Answer:**
     ```javascript
     function maxProduct(nums) {
       let max = nums[0];
       let min = nums[0];
       let result = max;

       for (let i = 1; i < nums.length; i++) {
         if (nums[i] < 0) [max, min] = [min, max];

         max = Math.max(nums[i], max * nums[i]);
         min = Math.min(nums[i], min * nums[i]);

         result = Math.max(result, max);
       }

       return result;
     }

     // Example usage
     console.log(maxProduct([2,3,-2,4])); // 6
     console.log(maxProduct([-2,0,-1])); // 0
     ```

#### 153. **Implement a Function to Find the Longest Consecutive Sequence**
   - **Question:** Write a JavaScript function that finds the length of the longest consecutive elements sequence in an unsorted array.
   - **Answer:**
     ```javascript
     function longestConsecutive(nums) {
       let numSet = new Set(nums);
       let longestStreak = 0;

       for (let num of numSet) {
         if (!numSet.has(num - 1)) {
           let currentNum = num;
           let currentStreak = 1;

           while (numSet.has(currentNum + 1)) {
             currentNum += 1;
             currentStreak += 1;
           }

           longestStreak = Math.max(longestStreak, currentStreak);
         }
       }

       return longestStreak;
     }

     // Example usage
     console.log(longestConsecutive([100, 4, 200, 1, 3, 2])); // 4
     console.log(longestConsecutive([0,3,7,2,5,8,4,6,0,1])); // 9
     ```     
