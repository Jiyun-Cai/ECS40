# Homework 4: Binary Search Trees

## Early bird bonus

If you pass all the test cases by 2016-11-18T23:59:59-08:00, you will get 3 bonus points (300/7 %).


## Submission instructions

```
$ cargo new 4 --name your
$ cd 4
$ # Save your program in `src/lib.rs`
$ git add Cargo.toml src/lib.rs
$ git commit
$ git remote add origin metastasis@gradebot.org:user/{username}/3/4
$ git push origin master
```

## Binary search trees

Implement a [binary search tree](https://en.wikipedia.org/wiki/Binary_search_tree) that supports insert, search, and [traversal](https://en.wikipedia.org/wiki/Tree_traversal).

## Public API

Your program must provide the following public API.

```
pub struct Tree<T> {
    ...
}

impl<T: Ord> Tree<T> {
    /// Creates an empty tree
    pub fn new() -> Self {
        unimplemented!()
    }

    /// Returns `false` if `key` already exists in the tree, and `true` otherwise.
    pub fn insert(&mut self, key: T) -> bool {
        unimplemented!()
    }

    /// Returns `true` if `key` exists in the tree, and `false` otherwise.
    pub fn find(&self, key: &T) -> bool {
        unimplemented!()
    }

    /// Returns the preorder traversal of the tree.
    pub fn preorder(&self) -> Vec<&T> {
        unimplemented!()
    }

    /// Returns the inorder traversal of the tree.
    pub fn inorder(&self) -> Vec<&T> {
        unimplemented!()
    }

    /// Returns the postorder traversal of the tree.
    pub fn postorder(&self) -> Vec<&T> {
        unimplemented!()
    }
}
```

## Challenge: non-recursive `Tree::insert()`

It is easy to implement `Tree::insert()` using recursion. However, implementing it without recursion is challenging, because it would require advanced techniques to appease Rust's borrow checker. I had to avoid the problems caused by [reborrow](https://doc.rust-lang.org/nomicon/references.html#liveness) and needed to use [`std::mem::replace`](https://doc.rust-lang.org/std/mem/fn.replace.html). If you overcome this challenge, please notify me by email, and I will compare your implementation with mine.

Last updated: 2016-11-10
