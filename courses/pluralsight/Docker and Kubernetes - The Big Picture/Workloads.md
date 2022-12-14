## Stateful vs Stateless

Both Docker and Kubernetes can support stateful and stateless apps. Stateful apps needs to remember something to run in the correct way, for example a database, the database needs to "remember its data" to run correctly. Stateless apps does not needs to remember state to run correctly, for example a website, if I shutdown a website and run in another machine, it should look exactly the same.

Handle state in these techs is hard, but it's totally possible.