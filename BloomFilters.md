# Bloom Filters

- How bloom filters work?
- Math behind false positive rates, optimal hash functions.
- Selection of hash functions.
- Implementation. 

### What is Bloom Filter?

Bloom Filter is a hash based probabilistic data structure used to compute the set membership of an element or answers the question 'isPresent'. Similar to hash based set data structures, the elements in the set have to be added to the Bloom filter, when required membership check of an element is performed. 

### How does Bloom Filter work? How is it different from regular HashSet and equivalent datastructures?

Bloom filter is optimized for storage. When a Bloom Filter is initialized it declares a specified number of bits, and binds a set of hash functions to the instance. When an element is added to the filter, the hash functions binded to the instance compute hash values of the target element. The resultant hash values are used to set relevant bits declared by the Bloom Filter. 

- HashSet can be iterated and values of keys added to the set can be retrieved on demand, whereas bloom filter wouldn't be able to retrieve the key directly. 

- A value cannot be removed from a Bloom Filter as multiple keys' hash values could use the same bit, for saving the hash.

- A Bloom Filter has probability to return false positives when queried about set membership. Bloom Filter use shared bits to persist the hashes of the key, if hashes of a specific key coincide with already set bits then bloom filter will return true for the key existence check.

 