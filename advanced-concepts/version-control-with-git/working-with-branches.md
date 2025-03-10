# Working with Branches

The initial commit while connecting to a repository is made to the master branch. If you want to work on a feature independently, you can create a separate branch.

To create a new branch -

* Click on the branch button at the bottom left corner. You can switch to an existing branch or create a new one from the branch pop-up.
* When you switch to another branch, the uncommitted changes in your current branch won’t carry over to the destination branch.

However, if you create a new branch, it will have the uncommitted changes of your parent branch.

{% hint style="info" %}
* Branch names should **not** start with `origin/` since this prefix is used to distinguish between local and remote versions of a branch.
* Checking out a remote branch with a local counterpart already available would result in an error.
* If you create a new branch, it will have the uncommitted changes of your parent branch. When you switch to another branch, the uncommitted changes in your current branch won’t be carried over to the destination branch. In both cases, the current branch will retain the uncommitted changes.
{% endhint %}

#### Syncing Local with Remote Branch

To sync the local with the remote branch (fetching or pruning), click on the branch pop-up and hit the “<mark style="color:purple;">Sync branches</mark>” button.

![](<../../.gitbook/assets/Git\_sync\_syc branches (1).gif>)

Syncing the branches won’t merge any change you’ve made on the remote branch. You’ll have to click on the pull button to get the latest changes.

### Delete a Branch

Similar to the Git flow, you can delete a branch in Appsmith that is no longer needed.

{% hint style="info" %}
You can delete any branch other than the default branch. Please make sure that you are not editing the branch you want to delete.
{% endhint %}

If you want to delete a branch from Appsmith, follow the steps given below:

1. Click on the branch list at the bottom left corner.
2. Move the cursor to the branch you want to delete, hit the options button, and click on delete branch.

{% embed url="https://youtu.be/Ww6cpZEkSqs" %}
