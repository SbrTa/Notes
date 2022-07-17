# Topological sort


```
    // Kahn’s algorithm -  O( V + E )
    vector<int> topologicalSort(vector<vector<int>> &adj, vector<int> &in){
        vector<int> order;
        queue<int> q;
        for(int i=0; i<in.size(); i++){
            if(!in[i]){
                q.push(i);
                order.push_back(i);
            }
        }
        while(!q.empty()){
            int u = q.front();
            q.pop();
            for(int v : adj[u]){
                in[v]--;
                if(!in[v]){
                    q.push(v);
                    order.push_back(v);
                }
            }
        }
        return order;
    }
```
