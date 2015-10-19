## C++ Problems

### Reverse linked list

Write a function that takes in a `forward_list` and prints its contents from back to front.

### Sorting a linked list

Write a function that sorts a `list` of doubles and returns it.

### Overloading <<

Given the following class:

```cpp
class CatTank {
public:
    // Initializes a CatTank from guns and feelings.
    CatTank(int guns, std::string feelings);

    // Kills another CatTank, decrements morality.
    void kill(CatTank other);
private:
    // Doesn't exist.
    int morality;
    std::string feelings;
};
```

Overload the operator << so that one can directly std::cout a CatTank.
