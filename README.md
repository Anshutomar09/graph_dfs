# graph_dfs
class Solution {
  public:
    // Function to return a list containing the DFS traversal of the graph.
    void dfs(int s, vector<vector<int>>&adj, vector<bool>&vis, vector<int>&v){
        vis[s]=true;
        v.push_back(s);
        for(auto it:adj[s]){
            if(!vis[it]){
                dfs(it, adj, vis, v);
            }
        }
    }
    vector<int> dfsOfGraph(vector<vector<int>>& adj) {
        vector<int>v;
        int n=adj.size();
        vector<bool>vis(n, false);
        for(int i=0;i<n;i++){
            if(!vis[i]){
            dfs(i, adj, vis, v);
            }
        }
        return v;
    }
};
