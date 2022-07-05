# KMP
KMP (Knuth Morris Pratt) algorithm is used to find a "Pattern" in a "Text". This algorithm campares character by character from left to right. 
But whenever a mismatch occurs, it uses a preprocessed table called "Prefix Table" to skip characters comparison while matching.

### Implementation
```

    vector<int> processLps(string pattern){
        vector<int> lps(pattern.length());
        int index = 0;
        for(int i=1; i<pattern.length();){
            if(pattern[i]==pattern[index]){
                lps[i] = index+1;
                i++;
                index++;
            }else{
                if(index!=0){
                    index=lps[index-1];
                }else{
                    lps[i] = index;
                    i++;
                }
            }
        }
        return lps;
    }
    
    int kmp(string text, string pattern){
        vector<int> lps = processLps(pattern);
        int i=0, j=0;
        while(i<text.length()){
            if(text[i]==pattern[j]){
                i++;
                j++;
            }else{
                if(j!=0) j = lps[j-1];
                else i++;
            }
            if(j==pattern.length()){
                return i-j;
            }
        }
        return -1;
    }
```
