This tutorial was written by stfx for developers to correctly backport commits. Example backporting from mangos-wotlk to mangos-tbc:

# 1. Set up the directory
  * Clone mangos-tbc repo
  * Add mangos-wotlk remote: `git remote add wotlk _url_`

# 2. Backport an actual commit
  * Fetch from mangos-wotlk every time something changes there: `git fetch wotlk`
  * Use backport tool in git bash: `contrib/backporting/mangos-backport.sh _commit_hash_`
  * Check and resolve conflicts if any exist
    * Amend the commit after resolving conflicts: `git commit -s --amend`

## 2.1. Backport a commit with sql changes
  * _Fetch from mangos-wotlk (like before)_
  * _Use backport tool (like before)_
  * _Check and resolve conflicts (like before)_
  * Rename the sql updates in sql/updates directory by adding this commit's version number at the start of the filename like so: `11754_01_mangos_mangos_string.sql -> s1415_11754_01_mangos_mangos_string.sql`
  * Remove the line related to db_version change (usually the first line in each sql update file)
  * _Amend commit (like before)_

# 3. Number the commit with git_id (only need for sql changes)
  * Build git_id tool in release mode if you did not already (located in contrib\git_id)
  * Push every outstanding commit because `git_id.exe` checks last version from remote
  * Use git_id in git bash: `contrib/git_id/Release/git_id.exe`
    * This automatically writes all db_version changes to mangos.sql and in the sql/updates/*.sql

# 4. Push the commits
  * Check correct authorship
  * Check commit number for commits with sql changes
  * Push to the mangos-tbc remote: `git push origin master` (assuming you named the mangos-tbc remote "origin" which is the default after cloning)