# Assignment 7 - digital fingerprint


### Review this first

A 'hash' is a short digital fingerprint of a string (or document); read about sha256 (a commonly used way to do this) [https://www.reddit.com/r/explainlikeimfive/comments/1isiji/eli5_sha256_hashing/](https://www.reddit.com/r/explainlikeimfive/comments/1isiji/eli5_sha256_hashing/). MD5 is another (older) hash function.


#### Example:

```python
import hashlib # library with hashing functions

str = 'cats rule'.encode()
print ( hashlib.sha256( str  ).hexdigest()  )
# prints: 50892f33c8f3295faabb16ab92f72289b24a4754dbca14cab4127a39ad1e92e1

str = 'cat rules'.encode()
print ( hashlib.sha256( str  ).hexdigest()  )
# prints: b9c5d00880137775c711833a1a8742fd5c9d40f37d06b8498cd8674285c95878
```

Notice how a small change gives a very different hash (good luck finding another string that gives the same hash).

A feature of hashing is that it is one-way; it is hard (as in nearly impossible) to find the original text based on the hash. Companies that store user data like passwords should really save the hashed versions and not the password itself (people often re-use their passwords). 

Why is the hash useful? If somebody changes the original document, the hash would not longer be the same. This is relevant for digital information (invoice, ledger).


> Note, the string is first 'encoded', which makes it binary. See how `print (type ( 'cats rule')) ` and `print (type ( 'cats rule'.encode() )) ` differ ('str' vs 'bytes'); the hash function requires bytes as an input.

### Compute the SHA256 hash for the Cinderella poem. (Read the file into one string, and encode() it before passing it into the sha256 function)


