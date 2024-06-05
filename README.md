#include <iostream>
#include <vector>

using namespace std;

class graph {
private:
    int V;
    vector<vector<int>> adj;

public:
    graph(int V) {
        this->V = V;
        adj.resize(V);
    }

    void addedge(int v, int w) {
        adj[v].push_back(w);
        adj[w].push_back(v);
    }

    void printgraph() {
        for (int v = 0; v < V; ++v) {
            cout << "Adjacency list of vertex " << v << ": ";
            for (auto& w : adj[v]) {
                cout << w << " ";
            }
            cout << endl;
        }
    }
};

int main() {
    graph g(5);

    g.addedge(0, 1);
    g.addedge(0, 4);
    g.addedge(1, 2);
    g.addedge(1, 3);
    g.addedge(1, 4);
    g.addedge(2, 3);
    g.addedge(3, 4);

    g.printgraph();

    return 0;
}# C-program-to-adjacency-of-vertex
