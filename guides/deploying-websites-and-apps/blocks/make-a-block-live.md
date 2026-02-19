Making a Block live switches your production code to use the new Block and takes the old Block offline. The switch is immediate, and the new Block will serve all web traffic that was previously served by the old Block.

Depending on your development process, you may choose to automate this process at the end of your CI/CD pipeline to achieve continuous deployment.

Alternatively, if you are practising continuous delivery, making a Block live is usually the last step in the delivery process and would be carried out by a site owner or product owner.

To make a Block live, you'll need to be a member of a role with the `Make live/rollback` permission.

1.  Select **Blocks** in the sidebar to open the *Blocks listing* screen.
2.  Press on the Block you want to view. The Blocks version listing will be displayed.
3.  Locate the Block version you want to make live and open the actions menu by pressing the **Actions** button indicated by the triple-dot.
4.  Select **Make live** from the dropdown menu. A confirmation window will be displayed.
5.  Press **Make live** to confirm you want to switch to using this Block in production.