# 最小生成树-- Kruskal 算法

## 一.最小生成数介绍

最小生成树算法是一个用于带权连通图的生成树问题。最小生成树问题的目标是找到一种生成树，使得该树上所有边的权值之和最小。目前常用的两种最小生成树算法是 Kruskal 算法和 Prim 算法，它们都基于贪心思想，通过不断加入边来生成最小生成树，时间复杂度分别为 O(ElogE) 和 O(ElogV)。而本文首先介绍Kruskal这一常用算法,预计下篇出Prim 算法。最小生成树算法在实际应用中可以用于通信网络规划、电力传输、城市规划、因特网路由等领域。比如采用最短线路将分布的灯泡连在一起。

在了解最小生成树之前，我们首先需要了解图的基本概念：

1.连通图：一个无向图中，如果任意两个节点之间都存在路径，那么这个图就是连通图。

2.生成树：对于一个连通图，生成树是指包含图中所有节点的一个子图，并且是一棵树（即没有环路）。

3.边的权值：在图的每条边上都有一个权值，用来表示该边的重要程度或代价。

这三点其实在本问题中体现的淋漓尽致。

## 二.Kruskal算法

我们介绍下最小生成数其中一个主流算法Kruskal，此算法比较Prim算法更适用于边稀疏的情况。

本算法其实非常简单,类似于最短线路,不懂最短线路可以看我上期,主要是分为四个核心步骤:

1.将图中的所有边按照权值进行排序。

2.从权值最小的边开始，依次遍历排序后的边。

3.如果这条边不会导致生成树形成环路，即加入该边不会形成闭合回路，则将它加入生成树中。

4.重复步骤3，直到生成树中的边数等于节点数减一，或者图中的边都被考虑完为止。

为了判断是否形成环路，Kruskal 算法使用并查集数据结构。每个节点在并查集中都有一个代表元素，初始时每个节点代表元素都是自己。当要判断两个节点是否属于同一个集合时，可以通过查找它们的代表元素来进行比较。如果两个节点的代表元素不同，说明它们属于不同的集合，可以将它们合并为同一个集合。排序可有内部实现。

为了防止解释不清，我们先简单了解下什么是并查集，推荐个视频【图论——并查集(详细版)】https://www.bilibili.com/video/BV1jv411a7LK?vd_source=a99a6abc406cf4968ddb5c1b363abc55

它的作用就是判断是否组成了一个环,边的加入时，高效地判断两个顶点是否在同一个集合中。通过并查集的 find 操作可以获得某个顶点所属集合的根节点，然后比较两个顶点的根节点是否相同，从而确定它们是否在同一个集合中。

## 三.代码实现

```Python
graph = {
    'A': {'B': 5, 'C': 2, 'D': 3, 'E': 9, 'F': 4},
    'B': {'A': 5, 'C': 1, 'E': 3},
    'C': {'A': 2, 'B': 1, 'D': 4},
    'D': {'A': 3, 'C': 4, 'E': 2},
    'E': {'A': 9, 'B': 3, 'D': 2, 'F': 6},
    'F': {'A': 4, 'E': 6}
}

#这里就定义并查集，因为Python中没有现成的
class UnionFind:
    def __init__(self):
        self.parent = {}

    def find(self, u):
        if u not in self.parent:
            self.parent[u] = u
            return u
        while self.parent[u] != u:
            u = self.parent[u]
        return u

    def union(self, p, q):
        root_p, root_q = self.find(p), self.find(q)
        self.parent[root_p] = root_q


# Kruskal 算法实现
def kruskal(g):
    edges = []
    for a in g:
        for b, w in g[a].items():
            edges.append((a, b, w))  # 将顶点和对应的权重添加到边列表中
    edges.sort(key=lambda x: x[2])  # 根据权重对边列表进行排序
    uf = UnionFind()
    mst = set()
    for a, b, w in edges:
        if uf.find(a) != uf.find(b):
            mst.add((a, b, w))  # 将选择的边添加到最小生成树中
            uf.union(a, b)
    return mst


mst = kruskal(graph)
print(mst)

```

```Python
{('B', 'C', 1), ('D', 'E', 2), ('A', 'C', 2), ('A', 'F', 4), ('A', 'D', 3)}
```

这样就将这几个点连接在一起了。

```C++
#include <iostream>
#include <vector>
#include <algorithm>
#include <unordered_map>

using namespace std;

struct Edge {
    char src, dest;
    int weight;

    Edge(char s, char d, int w)
        : src(s), dest(d), weight(w) {}
};

class UnionFind {
public:
    unordered_map<char, char> parent;

    char find(char u) {
        if (parent.find(u) == parent.end()) {
            parent[u] = u;
            return u;
        }
        while (parent[u] != u) {
            u = parent[u];
        }
        return u;
    }

    void unite(char p, char q) {
        char root_p = find(p);
        char root_q = find(q);
        parent[root_p] = root_q;
    }
};

vector<Edge> kruskal(unordered_map<char, unordered_map<char, int>>& graph) {
    vector<Edge> edges;
    for (auto& a : graph) {
        for (auto& b : a.second) {
            edges.push_back(Edge(a.first, b.first, b.second));
        }
    }
    sort(edges.begin(), edges.end(), [](const Edge& a, const Edge& b) {
        return a.weight < b.weight;
        });

    UnionFind uf;
    vector<Edge> mst;
    for (const auto& edge : edges) {
        if (uf.find(edge.src) != uf.find(edge.dest)) {
            mst.push_back(edge);
            uf.unite(edge.src, edge.dest);
        }
    }
    return mst;
}

int main() {
    unordered_map<char, unordered_map<char, int>> graph = {
        {'A', {{'B', 5}, {'C', 2}, {'D', 3}, {'E', 9}, {'F', 4}}},
        {'B', {{'A', 5}, {'C', 1}, {'E', 3}}},
        {'C', {{'A', 2}, {'B', 1}, {'D', 4}}},
        {'D', {{'A', 3}, {'C', 4}, {'E', 2}}},
        {'E', {{'A', 9}, {'B', 3}, {'D', 2}, {'F', 6}}},
        {'F', {{'A', 4}, {'E', 6}}}
    };

    vector<Edge> mst = kruskal(graph);
    for (const auto& edge : mst) {
        cout << edge.src << " - " << edge.dest << " : " << edge.weight << endl;
    }

    return 0;
}
```

C++亦是。
