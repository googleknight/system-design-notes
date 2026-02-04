## Common problems when teams scale up.

- New engineers need training and KT.
- Lot of non overlapping updates in stand ups.
- Feature development and deployment cycle is much longer than it should be.
- Lot of hand-holding for new engineers.
- Lack of isolation of concerns and ownership.

## Common solution is to split them into teams and code into micro services. These should be based on business units.

### Benefits:

- Shorter stand ups.
- Each team can have their own deployment cycle.
- Each team can scale and manage their services independently.

### Drawbacks:

- Lack of context sharing between teams
- Duplication of effort across teams for common functionalities.
- Communication b/w code becomes less efficient than earlier.
- Communication required b/w people of different teams becomes complex.
- Communication regrading code b/w people. Need good documentation, API contracts, tech specs, PRD. Publishing new changes in backward compatible format.

### Things to avoid when breaking Monolith to Microservice

- Different teams using different languages. This to avoid high learning curve for each team member. But if there's a very special requirement only then do it.
- Try to use the same technologies across the org. It's easier to manage.
- Keep an eye on DevOps, as it might go up. Once it's need increases only then have a dedicated team.

### Anti-pattern to avoid

- When new requirement comes, rather than handling them to existing teams, you create a new team and their service. If the feature can be handled and doesn't attract further work then it's best existing team handles, otherwise it leads to Nano-services. Having more services than people!

### When to create MicroService ?

- Push the new feature to existing teams, if in future work related to that increases then only create a new team.
- Two Microservices that only interact with each can be merged into one micro service.
