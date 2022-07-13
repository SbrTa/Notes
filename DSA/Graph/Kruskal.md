# Kruskal

```
    vector<array<int,3>> graph;
    vector<int> par;
    
    int parent(int n){
        if(par[n] == n) return n;
        return parent(par[n]);
    }
    
    int kruskal(){
        int sum = 0;
        sort(graph.begin(), graph.end(), [](const array<int,3> &a, const array<int,3> &b){
            return a[2] < b[2];
        });
        for(int i=0; i<graph.size(); i++){
            int u = parent(graph[i][0]);
            int v = parent(graph[i][1]);
            if(u!=v){
                par[v] = u;
                sum+=graph[i][2];
            }
        }
        return sum;
    }
```
