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


