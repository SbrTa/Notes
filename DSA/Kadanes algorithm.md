# Kadane's Algorithm
Kadane's algorithm finds Largest Sum Contiguous Subarray.

```
  Initialize:
      max_so_far = INT_MIN
      max_ending_here = 0

  Loop for each element of the array
    (a) max_ending_here = max_ending_here + a[i]
    (b) if(max_so_far < max_ending_here)
              max_so_far = max_ending_here
    (c) if(max_ending_here < 0)
              max_ending_here = 0
  return max_so_far
```

```
    int kadane(vector<int>& nums) {
        int max = INT_MIN;
        int sum = 0;
        for(int i=0; i<nums.size(); i++){
            sum = sum+nums[i];
            if(sum>max) max=sum;
            if(sum<0) sum=0;
        }
        return max;
    }
```
