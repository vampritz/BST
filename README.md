# BST
Check if a Binary Tree is BST or not .

#include<climits>
//helper
bool isBSThelp(BinaryTreeNode<int> *root,int minima,int maxima)
{
    
    
    if(root==NULL)
    {
        return true ;
    }
    if(root->data <minima || root->data >maxima)
    {
        return false ;
    }
    
    bool ans1=isBSThelp(root->left,minima,root->data);
    bool ans2=isBSThelp(root->right,root->data,maxima);
    
    return ans1&&ans2 ;
}

//main function
bool isBST(BinaryTreeNode<int> *root){
     
    return isBSThelp(root,INT_MIN,INT_MAX);

}
