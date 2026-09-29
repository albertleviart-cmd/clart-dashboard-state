# clart-dashboard-state

A tiny, isolated data file for one feature on https://albertleviart-cmd.github.io/clart-dashboard/ :
which "mark as done" checkboxes are currently checked, so it's the same across every device/browser
that opens the dashboard, not just the one that clicked it.

`done.json` is the only file that matters here. It's read from `raw.githubusercontent.com` (no auth
needed to read a public repo's raw file) and written via the GitHub Contents API using a
fine-grained access token that can ONLY write to this one repository, nothing else on this account.

This repo is intentionally separate from `clart-dashboard` (the real dashboard, its data, and the
automation instructions that run it) so that even if the write token above ever leaked, the worst
case is someone messes with this one throwaway file, not the real site or its automations.
