This tutorial was written by stfx for developers to correctly backport commits and shows an example on backporting from mangos-wotlk to mangos-tbc.

## 1. Set up the directory
  * Clone mangos-tbc repo
  * Add mangos-wotlk remote: `git remote add wotlk _url_`

## 2. Backport commits
  * Fetch from mangos-wotlk every time something changes there: `git fetch wotlk`
  * Use backport tool with hash of commit to backport: `contrib/backporting/mangos-backport.sh _commit_hash_`
  * Check and resolve conflicts if any exist
  * If you had to resolve conflicts you still have to amend the commit: `git commit -s --amend`

#### 2.1. Backport commits with sql changes
  * _Fetch from mangos-wotlk (like before)_
  * _Use backport tool (like before)_
  * _Check and resolve conflicts (like before)_
  * Rename the sql updates in sql/updates directory by adding the client version's prefix character at the start of the filename like so: `11754_01_mangos_mangos_string.sql -> s11754_01_mangos_mangos_string.sql`
  * _Amend commit (like before)_

#### 2.2. Number commits with sql changes using git_id
  * Build git_id tool in release mode if you did not already (located in contrib\git_id)
  * Push every outstanding commit because `git_id.exe` checks last version from remote
  * Use git_id in git bash: `contrib/git_id/Release/git_id.exe`
    * This automatically writes all db_version changes to mangos.sql and in the sql/updates/*.sql

## 3. Push the commits
  * Check correct authorship
  * Check commit number for commits with sql changes
  * Push to the mangos-tbc remote: `git push origin master` (assuming you named the mangos-tbc remote 'origin' which is the default after cloning)