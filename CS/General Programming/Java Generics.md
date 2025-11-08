Collections in java are invariant, i.e. `List<String>` is not a subtype of `List<Object>` 
So this is not permissible

```
List<String> strs = new List<Object> // will not compile
```
PECS (Producer-extends Consumer super) mnemonic introduced by Joshua Bloch (Effective Java)
Collections which are only read from are called Producers and and collections which are only written to are called Consumers.

Best way to understand is:
If you have a collection of strings `Collection<String>` reading a collection of objects is fine `Collection<Object>`. Similarly if you have a collection of objects, writing a collection of strings to it is fine.