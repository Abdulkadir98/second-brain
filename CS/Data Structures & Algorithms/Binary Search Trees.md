Can be used to implement Symbol Tables and also preserves ordering of keys

Insert: O(Log N)
Retrieve Key: O(Log N)


### Deletion pseudo code (Hibbard deletion)

	private Node delete(Node x, Key key) {  
    if (x == null) {  
        return null;  
	 }  

	 int cmp = key.compareTo(x.key);  
	 if (cmp < 0) {  
			x.left = delete(x.left, key);  
	 }  
		else if (cmp > 0) {  
			x.right = delete(x.right, key);  
	 } else {  
			if (x.left == null) return x.right;  
	 if (x.right == null) return x.left;  

	 Node t = x; // node to delete  
	 x = min(t.right);  
	 x.right = deleteMin(t.right);  
	 x.left = t.left;  
	 }  
		x.size = 1 + size(x.left) + size(x.right);  
	 return x;  
	}
	
* Recursively search for the node to delete
* After finding the node - if the left child is null, return the pointer to the right child. If the right child is null return the pointer to the left child
* If the both left and right child are non-null :
	* Save the reference to the node to be deleted in a temporary variable
	* Find the minimum of the subtree rooted at the right child of the node to be deleted and place that node in the place of the node to be deleted
	* Delete that minimum node that was just placed in the deleted node's position by calling the deleteMin() subroutine - the node returned by this subroutine is the right child of the newly placed node
	* The left child of the newly placed node is the deleted node's left child which can be accessed from the temporary variable



### References
https://algs4.cs.princeton.edu/32bst/
https://algs4.cs.princeton.edu/32bst/BST.java.html
https://www.youtube.com/watch?v=usq3dxJ2r5k&list=PLXFMmlk03Dt7Q0xr1PIAriY5623cKiH7V&index=63&ab_channel=StanfordAlgorithms