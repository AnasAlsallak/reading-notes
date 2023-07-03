# Readings 30: Implementation: Hash Tables

## Table of Contents

- [Hashtable](#hashtable)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## Hashtable

A hashtable, also known as a hash map, is a data structure that stores key-value pairs. It utilizes a hash function to compute an index, where the value will be stored in an array. This allows for efficient retrieval of values based on their keys.

Here are the answers to your specific questions:

    1. What is a Hashtable?
    A hashtable is a data structure that provides fast access to values based on their keys. It uses a hash function to map keys to specific indexes in an array, where the corresponding values are stored.

    2. Why do we use them?
    Hashtables are used for various reasons, including:
    - Efficient lookup: Retrieving values based on keys has an average time complexity of O(1), making it faster compared to other data structures like arrays or linked lists.
    - Unique key-value pairs: Hashtables enforce uniqueness of keys, which is useful in scenarios where duplicate keys are not allowed.
    - Dictionary-like functionality: Hashtables can be used to implement dictionaries or associative arrays, providing a convenient way to store and retrieve data using meaningful keys.

    3. Structure:
    A hashtable typically consists of an array of buckets, where each bucket can hold one or more key-value pairs. The number of buckets is determined by the size of the hashtable. The hash function calculates the index for each key, and the key-value pair is stored in the corresponding bucket.

    4. Hashing:
    Hashing is the process of converting a key into a numeric value, typically an index in the array. The hash function takes the key as input and produces a hash code. The hash code is then converted into a valid index using techniques such as modulo arithmetic.

    5. Creating a Hash:
    To create a hash, a hashing algorithm is applied to the key. A simple hashing algorithm involves adding or multiplying the ASCII values of the characters in the key and applying modulo arithmetic to fit the result within the range of array indexes.

    6. Collisions:
    Collisions occur when two or more keys produce the same hash code, resulting in the same index in the array. Collisions are resolved by using techniques like chaining or open addressing. Chaining involves storing multiple key-value pairs in the same bucket using a linked list or another data structure. Open addressing methods involve finding an alternative empty slot in the array when a collision occurs.

    7. Hashmap Example:
    Here's an example of a hashmap:

    ```
    HashMap<String, Integer> population = new HashMap<>();
    population.put("New York", 8623000);
    population.put("Los Angeles", 3990000);
    population.put("Chicago", 2716000);

    int newYorkPopulation = population.get("New York");
    System.out.println("Population of New York: " + newYorkPopulation);
    ```

    In this example, a hashmap is created to store the population of different cities. The keys are city names (strings) and the values are population counts (integers). Values are added using the `put` method, and a specific value is retrieved using the `get` method.

    8. Bucket Sizes:
    The number of buckets in a hashtable can vary depending on the implementation and the desired trade-offs. Having more buckets can reduce collisions but may increase memory usage, while having fewer buckets may increase the likelihood of collisions. It's important to choose an appropriate number of buckets based on the expected size of the hashtable and the data distribution.

    9. Methods:
    Some common methods provided by hashtables include:
    - `put(key, value)`: Inserts a key-value pair into the hashtable.
    - `get(key)`: Retrieves the value associated with a given key.
    - `remove(key)`: Removes a key-value pair from the hashtable.
    - `containsKey(key)`: Checks if the hashtable contains a specific key.
    - `size()`: Returns the number of key-value pairs in the hashtable.
    - `isEmpty()`: Checks if the hashtable is empty.
    - `clear()`: Removes all key-value pairs from the hashtable.
    - `keySet()`: Returns a set of all keys in the hashtable.
    - `values()`: Returns a collection of all values in the hashtable.

    These methods provide convenient ways to interact with and manipulate the data stored in the hashtable.

    10. HashTable vs. HashMap:
    In Java, there are two similar classes for implementing hashtables: `HashTable` and `HashMap`. Both classes provide key-value pair storage and retrieval. However, there are some differences:
    - `HashTable` is synchronized, which means it is thread-safe and can be accessed by multiple threads concurrently. `HashMap` is not synchronized by default, but it can be made synchronized using external synchronization.
    - `HashTable` does not allow `null` keys or values, whereas `HashMap` allows `null` keys and values.
    - `HashTable` is considered a legacy class and is generally not recommended to use in new code. `HashMap` is the preferred choice for most scenarios.

## Things I want to know more about

Get more in-depth into hashtables.

[Move Class 31](./Class31.md) | [Previous](./Class29.md)
