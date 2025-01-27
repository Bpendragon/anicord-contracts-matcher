# Automatic Matcher for Anicord Contracts

This is how you got that weird anime assigned to you

---

The script uses a simple heuristic to "fairly" distribute
the pool among all users while avoiding matching shows
they have seen.

Queries made to AniList will be retried on 429
forever using the minimum wait times returned by their system until either a success or
an error. Successful requests are cached in `cache/` for 1
year and the script can safely be re-run.

## Usage:

- `pip install .`
- Put the pool of anilist links in `pool.txt`
  - After each line place a space, pipe, a second space, and then either `S` or `T` to indicate "Staff" (some seasons "Veteran") or "Trash" specials respectively
- Put the pool of users in `usernames.txt`
  - Each row consists of up to 3 columns
  - Columns are delimited by ` | ` (space, pipe, space)
  - The first column is required and is the link to the user's anilist profile.
  - The second column is the user's discord username. It is optional and may be removed entirely, if omitted out it will be blank in the output CSV.
  - The final column is which contracts they are signed up for, it is optional, but if provided it must be either `S`, `T`, or `B` to indicate "Staff" (some seasons "Veteran"), "Trash", or "Both" specials respectively. If omitted will default to `S`
- Run `main.py`

### Spring 2024

`data/pool.txt` in the repo contains staff picks for the season

`data/usernames.txt` has been redacted for privacy reasons.

Both of these contain examples of the proper formatting.
