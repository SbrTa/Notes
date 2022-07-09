# Rabin Karp - Rolling Hash
The Rabin-Karp string matching algorithm calculates a hash value for the pattern, as well as for each M-character subsequences of text to be compared. 
If the hash values are unequal, the algorithm will determine the hash value for next M-character sequence. If the hash values are equal, the algorithm 
will analyze the pattern and the M-character sequence. In this way, there is only one comparison per text subsequence, and character matching is only 
required when the hash values match.

#### Rabin-Karp Algorithm Applications
  - For pattern matching
  - For searching string in a bigger text

#### Spurious Hit
When the hash value of the pattern matches with the hash value of a window of the text but the window is not the actual pattern then it is called a spurious hit.
Spurious hit increases the time complexity of the algorithm. In order to minimize spurious hit, we use modulus. It greatly reduces the spurious hit. 
The modulus **prime number should be large**.

#### Rabin-Karp Algorithm Complexity
  - The average case and best case complexity is O(m + n)
  - The worst case complexity is O(mn). The worst-case complexity occurs when spurious hits occur a number for all the windows.



```
  int const base = 256;    // total different characters
  int const mod = 1000003; // large prime number

  int rabinKarp(string text, string pattern)
  {
      int n = text.length();
      int m = pattern.length();
      if (n < m)
          return -1;

      int i, j;
      int ph = 0; // pattern hash
      int th = 0; // text hash
      int h = 1;  // h = power(base, m-1) % mod
      for (i = 0; i < m - 1; i++)
          h = (h * base) % mod;

      for (i = 0; i < m; i++)
      {
          th = (base * th + text[i]) % mod;
          ph = (base * ph + pattern[i]) % mod;
      }

      for (i = 0; i <= n - m; i++)
      {
          if (th == ph)
          {
              for (j = 0; j < m; j++)
                  if (text[i + j] != pattern[j])
                      break;
              if (j == m) // patetern found
                  return i;
          }

          if (i < n - m)
          {
              th = th - (h * text[i]);       // remove first character
              th = th * base;                // left shift
              th = (th + text[i + m]) % mod; // add next character
              if (th < 0)
                  th = th + mod;
          }
      }
      return -1;
  }
```
