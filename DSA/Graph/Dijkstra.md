# Dijkstra

```
    int dijkstra(vector<vector<pair<int,int>>> adj, int n, int k) {
        vector<int> cost(n+1, MX);
        priority_queue<int> q;
        
        cost[k]=0;
        q.push(k);
        
        while(!q.empty()){
            int u = q.top();
            q.pop();
            for(int i=0; i<adj[u].size(); i++){
                int v = adj[u][i].first;
                int c = adj[u][i].second;
                if(cost[u]+c<cost[v]){
                    cost[v] = cost[u]+c;
                    q.push(v);
                }
            }
        }
        // cost contains shortest path from k to all node
    }

```
