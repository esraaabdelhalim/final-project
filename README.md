# Binary Search Tree (BST) Traversal Routines

## Trees

- [ ] Introduce **graphs** briefly and **tree** as a special case of a **graph** data structure.
- [ ] Add some figures for **graphs** and figures for **trees**.

- [Gragh: In graph there can be more than one path i.e. graph can have uni-directional or bi-directional paths (edges) between nodes.it can have loops, circuits as well as can have self-loops.In graph there is no such concept of root node.]
- [Tree: is special form of graph i.e. minimally connected graph and having only one path between any two vertices. having no loops, no circuits and no self-loops.In tree there is exactly one root node and every child have only one parent.]
![](Graph.jpg)
![](tree.jpg)

## Binary Search Trees

- [ ] Binary Trees as a special case of Trees.
- [ ] Binary Search Tree (BST) as a special case of Binary Trees
- [X] Add a an example figures for a Binary Tree
- [ ] Add a an example figures for a BST

<!-- This is a comment line in Markdown and HTML -->
<!-- Comment line are not rendered in the viewed document -->
<!-- Here is a sample images inside a table  -->
| Binary Tree | Binary Search Tree (BST) |
|-------------|--------------------------|
| ![bt](images/sample_image.png) | [*Add figure here*] |


- [Binary Tree:  is a tree data structure in which each node has at most two children, which are referred to as the left child and the right child.]
- [ Binary search tree (BST): is a binary tree where each node has a Comparable key (and an associated value) and satisfies the restriction that the key in any node is larger than the keys in all nodes in that node's left subtree and smaller than the keys in all nodes in that node's right subtree. ]
![](0509mattethatf2.jpeg)
![](img151.gif)

### Motivation

- [ ] Why using BST
- [ ] BST vs. Arrays
- [ ] BST vs. Linked Lists

- [we use BST because it is more arrangement]
- [-Array:allows random access to each element in it.so you can insert,delete and look for a specific element.
-BST:stored by defination,and for a regular BST, you get O(n) worst case behavior. for balanced BST, you get O(logn) insert/delete/find.]
- [In a linked list, the items are linked together through a single next pointer. In a binary tree, each node can have 0, 1 or 2 subnodes, where (in case of a binary search tree) the key of the left node is lesser than the key of the node and the key of the right node is more than the node. As long as the tree is balanced, the searchpath to each item is a lot shorter than that in a linked list.]

### Node Structure

- [ ] Propose a c++ `struct` of a BST node.

```c++
struct BSTNode
{
// Add memebers here
    int data;
    BSTNode *left;
    BSTNode *right;
};
```

### Basic Operations on BST

#### Insertion

- [ ] Description
- [ ] Sample code (Maybe Psuedo)
- [ ] Performance analysis (i.e big-`O` notation)

- [Insertion: means that we need to insert new element to the tree.if this element > root then it will insert from the right side of tree.if this element < root then it will insert from the left side of tree]
- [
    void insert( BSTNode *&tree, int data )
{
    if ( isEmpty( tree ))
        tree = new BSTNode{ data , nullptr , nullptr };

    else
    {
        if ( data < tree->data )
            insert( tree->left, data );

        else insert( tree->right, data );
    }
}
]
- [O(log2(n))]

#### Removal

- [ ] Description
- [ ] Sample code (Maybe Psuedo)
- [ ] Performance analysis (i.e big-`O` notation)

- [Removal: means that we need to delete an element from the tree it has 3 cases:
1- no children: this means that the node doesnt have any children"no connection with any node".it is considered that is the simplest case;because it is not required to connect any node with another.
2- one child: this means that the node has only 1 child"connect with 1 node".it is required to connect the children with the parent.
3- two children: this means that the node has 2 children the left one and the right"connect with 2 nodes".it is required to ]
- [
    void remove( BSTNode *&tree, int data )
{
    if ( isEmpty( tree )) return;

    if ( data == tree->data )
    {
        if ( !isEmpty( tree->left ) && !isEmpty( tree->right ))
        {
            BSTNode *minRight = minNode( tree->right );
            tree->data = minRight->data;
            remove( tree->right, minRight->data );
        } else
        {
            BSTNode *discard = tree;

            if ( isLeaf( tree ))
                tree = nullptr;
            else if ( !isEmpty( tree->left ))
                tree = tree->left;
            else
                tree = tree->right;

            delete discard;
        }

    } else if ( data < tree->data )
        remove( tree->left, data );
    else remove( tree->right, data );
}
]
- [O(log2(n))]

#### Traversal

- [ ] Description
- [ ] Why traversing a tree (applications)
- [ ] Extra: After writing the next subsections add a comparison table between the 4 traversal routines.

- [Traversal: means that we need to pass through all elements in the tree.]
- [Applications: search,print]

##### In-order

- [ ] Description
- [ ] Implement the logic without using recursion (You may use Psuedo-code)
- [ ] Performance analysis (i.e big-`O` notation)

- [In-order: it is the first method of traversal.if we print "for example" in the first the left side will be printed, then the root will be printed, finally the right side will be printed]
- []
- [O(log(n))]

##### Pre-order

- [ ] Description
- [ ] Implement the logic without using recursion (You may use Psuedo-code)
- [ ] Performance analysis (i.e big-`O` notation)

- [Pre-order:  it is the second method of traversal.if we print "for example" in the first the root will be printed, then the left side will be printed, finally the right side will be printed]
- []
- [O(log(n))]

##### Post-order

- [ ] Description
- [ ] Implement the logic without using recursion (You may use Psuedo-code)
- [ ] Performance analysis (i.e big-`O` notation)

- [Post-order:  it is the third method of traversal.if we print "for example" in the first the left side will be printed, then the right side will be printed, finally the root will be printed]
- []
- [O(log(n))]

##### Breadth-first

- [ ] Description
- [ ] Implement the logic without using recursion (You may use Psuedo-code)
- [ ] Performance analysis (i.e big-`O` notation)

- [Breadth-first search (BFS): is an algorithm for traversing or searching tree or graph data structures. It starts at the tree root (or some arbitrary node of a graph, sometimes referred to as a 'search key'[1]) and explores the neighbor nodes first, before moving to the next level neighbours.]

### References

- [ ] List the references.
- [ ] Add videos or blogs you think very simple and informative.

1. [Binary search tree](https://en.wikipedia.org/wiki/Binary_search_tree), *Wikipedia*.
2. [*Reference 2*]
3. [*Reference 3*]
4. [*and so on..*]
# final-project
