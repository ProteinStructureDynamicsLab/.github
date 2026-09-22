# GitHub conventions — Protein Structure and Dynamics Lab

Short handbook for everyone in the group.

## Accounts and access

- Use a personal GitHub account, not a shared one. It follows you when you
  leave, and authorship stays attributable.
- Two-factor authentication is required across the organisation.
- Access is granted through **teams**, never by adding people to repositories
  one at a time. When someone joins or leaves, one change covers everything.

Teams:

| Team           | Who              | Default access |
| -------------- | ---------------- | -------------- |
| `core`         | Permanent staff  | Maintain       |
| `researchers`  | PhD, postdocs    | Write          |
| `students`     | Master's, interns| Write on their project only |
| `collaborators`| External         | Read, or Write on one repo |
| `alumni`       | Departed members | Read |

People are moved to `alumni` on their last day. Their commits and authorship remain
intact; only their push access ends.

## Repositories

- One repository per coherent project, named in lowercase with hyphens:
  `ai-enzyme-design`, not `AI_Enzyme_Design_v2_final`.
- Every repository has a README, a LICENSE and a description before anyone
  else is invited to it.
- Default branch is `main`, and it always works.
- Archive rather than delete finished projects. An archived repository is
  read-only, clearly marked, and still citable.

### Forks vs. our own code

Fork an upstream project when we need to track and occasionally patch it
(EvolvePro, boltz). Do **not** grow lab-specific analysis inside a fork: it
collides with every upstream merge, it can't be cited on its own, and it's
invisible to anyone reading our profile. Write that code in its own repository
and import the upstream package as a dependency.

## Branches and pull requests

- Branch names: `yourname/short-description`.
- Nobody pushes to `main`. Everything goes through a pull request with one
  approving review.
- Squash-merge, delete the branch afterwards.
- Reviewing a labmate's PR within a day or two is part of the job.

## Data and secrets

- No raw data, embeddings, checkpoints or figures in git. They go to
  institutional storage or Zenodo; the repository holds the path in a config.
- No credentials, API tokens or institutional paths with personal home
  directories (`/home/tigem/name/...`).
- `pre-commit` catches most of this automatically. Install it.

## Citation and publication

- Tag a release when a result goes into a preprint or paper.
- Connect the repository to Zenodo before the first release so the tag mints a
  DOI, and put that DOI in the paper's data availability statement.
- Keep `CITATION.cff` current, including ORCIDs.

## When someone leaves

1. Move them from their team to `alumni`.
2. Check whether they own any repository under a personal account that the lab
   depends on, and transfer it to the organisation.
3. Confirm no pipeline depends on a personal access token of theirs.
