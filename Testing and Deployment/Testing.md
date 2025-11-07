
### Backend

For backend testing, we decided to use Bun's built-in Jest-compatible testing framework as it provides an easy way to write comprehensive tests that can easily be integrated and run in our codebase.

Manually running all the tests can be achieved with the command `bun start` in the `api/` directory of the repository.

#### Test structure

Tests are written for the relevant modules as `xyz.test.ts` files, for example `routes.test.ts` in the `organisation` directory indicates the file contains automated test definitions relating to endpoints for managing organisation data.

>[!Info]
>Information on Bun's testing framework can be found in their official documentation here: https://bun.sh/docs/test


#### CI/CD Integration

We also have our backend testing configured to run *on every push* for every branch using Github Actions CI/CD.
- This allows us to instantly spot if breaking code has been committed to the remote repository (even in un-merged feature branches) before it becomes a problem in deployment



### Frontend

For our frontend testing we chose to go with the handy method of manually testing. For each component, our testers would vigorously play with the buttons or inputs and see what would go wrong, and if each output is the intended case. 

For the native app, we tested our styling by comparing the visuals between different platforms, ie mobile and tablet. When the styling would look off or break for either one of the platforms, fixes would be made so that the styling would be seamless.

