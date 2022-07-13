# Kruskal

```
    struct edge {
        int u, v, w;
        bool operator < (const edge & s) const{
            return w<s.w;
        }
    };
    vector<edge> graph;
    vector<int> par;
    
    int parent(int n){
        if(par[n] == n) return n;
        return parent(par[n]);
    }
    
    int kruskal(){
        int sum = 0;
        sort(graph.begin(), graph.end());
        for(int i=0; i<graph.size(); i++){
            int u = parent(graph[i].u);
            int v = parent(graph[i].v);
            if(u!=v){
                par[v] = u;
                sum+=graph[i].w;
            }
        }
        return sum;
    }
```
