# Job Search Tracker

Static dashboard. `index.html` reads `data/jobs.json` and shows monthly application progress, status counts, and each job.

## Data format

`data/jobs.json` holds `goal.monthlyApplications`, `minPay`, and a `jobs` list. Each job has:

- `id`: unique slug
- `company`, `role`, `pay`, `payMin` (number, annual)
- `link`: apply URL
- `dateFound`, `dateApplied`: `YYYY-MM-DD` (`dateApplied` empty until applied)
- `status`: one of `Found`, `Drafting`, `Applied`, `Interview`, `Offer`, `Rejected`, `Passed`
- `contact`, `fit` (`High`, `Medium`, `Low`), `notes`

The monthly counter counts jobs with an applied-type status and a `dateApplied` in that month.

## Publish

GitHub Pages: Settings, Pages, deploy from branch `main`, folder `/ (root)`. No build step.
