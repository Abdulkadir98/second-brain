Used to store String keys for efficient insertion, search, and retrieval

applications:
Spell checker
auto-complete

Time complexity:
Search: O(L) where L is the length of the string
Insert: O(L)

Representation:
```
class TrieNode:

	def __init__(self):
		self.links = [None] * 26 // R-way trie where R = 26, determines the number of links each node has
		
	def put(self, ch, node):
		self.links[ord(ch) - ord('a')] = node
		
	def get(self, ch):
		return self.links[ord(ch) - ord('a')]
	
	def contains_key(self, ch):
		return self.links[ord(ch) - ord('a')] is not None
		
```

**Note**: The letters/characters are not stored explicitly, they are implicit by way of "links" or indexes in the array. So for insert/get we start at the root then follow each letter/key until we reach the end of the string

Disadvantage: can consume a lot more space due to 'R' null links at each node. For e.g. strings today are represented in unicode which would result in 65, 536 way trie!