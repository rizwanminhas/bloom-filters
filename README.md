# About
A Bloom filter is a space-efficient probabilistic data structure that is used to test whether an element is a member of a set.

## Some Properties
1. A Bloom filter of a fixed size can represent arbitrarily large number of elements.
2. Adding an element never fails. However, the false positive rate increases steadily as elements are added until all bits in the filter are set to 1, at which point all queries yield a positive result.
3. Bloom filters never generate false negative result, i.e., telling you that a username doesn’t exist when it actually exists.
4. Deleting elements from filter is not possible.

# How does it work?
1. Create a bit array of size `N` and set every bit to 0.
2. Select `K` hash functions. 
3. To insert an element pass it through K hash functions and for each result mod it with N and set the bit to 1.
4. To check if a value exists pass it through each hash function and mod it with N and check if each index is set to 1, if each index is set to 1 then the value `probably exists` in the set. It is probabalistic because another value could have also resulted in the same bits.