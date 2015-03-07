This tutorial was written by stfx for mangos-tbc (and mangos-classic) developers to correctly backport commits from master (wotlk).

# 1. Set up the directory
  * Clone mangos-tbc repo
  * Add mangos-wotlk remote: `git remote add wotlk _url_`

# 2. Backport an actual commit
  * Fetch from mangos-wotlk every time something changes there: `git fetch wotlk`
  * Use backport tool in git bash: `contrib/backporting/mangos-backport.sh _commit_hash_`
  * Check and resolve conflicts if any exist
  * If you had to resolve conflicts you still have to amend the commit and maybe change the commit message as well: `git commit -s --amend`

## 2.1. Backport a commit with sql changes
  * _Fetch from mangos-wotlk (like before)_
  * _Use backport tool (like before)_
  * _Check and resolve conflicts (like before)_
  * Rename the sql updates in sql/updates directory by adding this commit's version number at the start of the filename like so: 11754_01_mangos_mangos_string.sql -> s1415_11754_01_mangos_mangos_string.sql
  * Remove the lines related to db_version change (in the sql update file usually the first one and the empty line after that)
  * _Amend commit (like before)_

# 3. Number the commit with git_id
  * Build git_id tool in release mode if you did not already (located in contrib\git_id)
  * Use git_id in git bash: `contrib/git_id/Release/git_id.exe -l`

## 3.1. Number the commit with sql changes
  * Push every outstanding commit because git_id.exe -s does not work if you used git_id.exe -l before
  * Use `contrib/git_id/Release/git_id.exe -s` in git bash so that all db_version changes will be automatically written to mangos.sql and in the sql/updates/*.sql

# 4. Push the commits
  * Check correct authorship
  * Check commit number
  * Push to the mangos-tbc remote: `git push origin master` (assuming you cloned from mangos-tbc or named the mangos-tbc remote "origin")