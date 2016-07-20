# SearchTree

public class treeSearch 
{
	int root;
	treeSearch left;
	treeSearch right;
	public void insert(int insertElement)
	{
		if(insertElement==root)
		{
			System.out.println("Sorry, the value is already in the tree");
		}
		else if(left==null && right==null && root==0)
		{
			root=insertElement;
		}
		else if(insertElement<root)
		{
			if(left==null)
			{
				left=new treeSearch();
				left.insert(insertElement);
			}
			else
			{
				left.insert(insertElement);
			}
		}
		else if(insertElement>root)
		{
			if(right==null)
			{
				right=new treeSearch();
				right.insert(insertElement);
			}
			else
			{
				right.insert(insertElement);
			}
		}
	}
	public void binSearch(int searchElement)
	{		
		System.out.println("Root="+root);
		if(searchElement==root)
		{
			System.out.println("Element is found at root");
		}
		else if(searchElement<root)
		{
			System.out.println("Tree traversal through left of root "+root);
			if(left!=null)
			{
				left.binSearch(searchElement);
			}
			else
			{
				System.out.println("Element not found");
			}
		}
		else if(searchElement>root)
		{
			System.out.println("Tree traversal through left of right "+root);
			if(right!=null)
			{
				right.binSearch(searchElement);
			}
			else
			{
				System.out.println("Element not found");
			}
		}
	}
}
class BinarySearch
{
	public static void main(String x[])
	{
		treeSearch tree =new treeSearch();
		tree.insert(23);
		tree.insert(13);
		tree.insert(21);
		tree.insert(24);
		tree.insert(2);
		tree.insert(25);
		tree.insert(45);
		tree.binSearch(2);
	}
}
