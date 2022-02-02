# assignment2-vilipala
# Sindhuja Vilipala
###### LB Nagar
LB Nagar is a ring road where too much vehicles were pass away and there is a hotel **kirthunga** where we can find a **Delicious** food.

---

Way to My favorite food location
1. Go to shamshabad
2. Take a bus
    1.  Travel from shamshabad to L.B. Nagar
    8. On the right side of the Bus Station  there is a restaurant called krithunga
1. There we can go and eat
* Chiken Biryani
* Veg Biryani
* Dosa
    * Masala Dosa
    * Maggi Dosa
    * plain Dosa
* Double ka Meetha
* Mango Milkshake
* Haleem

[To know more about me](https://github.com/SindhujaVilipala/assignment2-vilipala/blob/main/AboutMe.md)

---

# SPORTS
I would like  to refer the following sports to others are Golf, Cricket, Hockey, Table tennis.
|  Name      |  Location  | Amount to pay  |
| ---------- | ---------- | -------------- |
|  Golf      | Florida    |   $95          |
| Cricket    | Hyderabad  |   $50          |
|  Hockey    | Georgeo    |   $25          |
|Table tennis| Maryville  |   $20          |

---

# Pithy Quote
> A blank piece of paper is God's way of telling us how hard it to be God.-*Sidney Sheldon*<br>
> First, find out what your hero wants, then just follow him!
-*Ray Bradbury*

---

# Graphs Spanning

> A tree is a connected undirected graph with no cycles. It is a spanning tree of a graph G if it spans G (that is, it includes every vertex of G) and is a subgraph of G (every edge in the tree belongs to G).

Link to Spinning Tree <https://en.wikipedia.org/wiki/Spanning_tree>
~~~

vector<vector<int>> adj;

vector<int> pruefer_code() {
    int n = adj.size();
    set<int> leafs;
    vector<int> degree(n);
    vector<bool> killed(n, false);
    for (int i = 0; i < n; i++) {
        degree[i] = adj[i].size();
        if (degree[i] == 1)
            leafs.insert(i);
    }

    vector<int> code(n - 2);
    for (int i = 0; i < n - 2; i++) {
        int leaf = *leafs.begin();
        leafs.erase(leafs.begin());
        killed[leaf] = true;

        int v;
        for (int u : adj[leaf]) {
            if (!killed[u])
                v = u;
        }

        code[i] = v;
        if (--degree[v] == 1)
            leafs.insert(v);
    }

    return code;
}
~~~
Link to source code <https://cp-algorithms.com/graph/pruefer_code.html>