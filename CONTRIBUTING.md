# Contributing

**Outside pull requests are not being accepted while Atheron is in development.** They will be closed without review. The reasoning is on the organization profile page, and it comes down to unstable interfaces and pending audits rather than any lack of interest.

Security reports are the exception. Email security@aton-network.org.

## For the core team

Three rules, applied per repository.

**One, every pull request adds a changelog entry.** A file under `changelog/` named `YYYY-MM-DD-short-slug.md`, with frontmatter and three short paragraphs: what changed, why it was worth doing, and what it means for the project. Written for someone who does not read code. CI fails the pull request without one, and the site publishes it verbatim, so it is worth a minute of thought.

**Two, progress is updated in the same pull request as the work.** `.atheron/progress.json` lists build-plan items and their state. Do not batch these up to update later. The public completion percentage is computed from these files, so a stale one is a public misstatement.

**Three, nothing under the chain or contract repositories may depend on infrastructure we operate.** Not an endpoint we host, not an API we run. If a case genuinely needs an exception it is documented and signed off before the code exists.

## Governance code

The safety valve covers the tensor-memory-hard mining lane and the cross-VM router. Those two, nothing else. We have said so publicly. Any change that widens the surface it can reach is a disclosure problem before it is an engineering one, so it does not get merged quietly.
