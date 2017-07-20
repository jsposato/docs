## Sonar Best Practices

### Start early
The earlier in the project lifetime you start scanning with Sonar, 
the less technical debt you will add to the codebase. It's simple 
to setup to analyze the code.

### Run often
Run against PRs . There is no reason to merge a PR with any reported
issues on it, even if they are minor.

and run when develop is updated

### What if we didn't start early?
If you didn't start analyzing with Sonar when the project started, 
you may have thousands of issues or more. The first thing to do is
plug the hole.  Get Sonar running against PRs to keep new issues
from making it into the codebase.  Once that is done you can start
tackling the critical and major issues during stabilization sprints
or whenever it makes sense in your project.