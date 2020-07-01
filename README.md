# monkey_gitignore_template
basic .gitignore templates

## extensive .gitignores
- [node.js](https://github.com/github/gitignore/blob/master/Node.gitignore)

## See also

- a giant list of .gitignore templates from the official [github.com/github/gitignore](https://github.com/github/gitignore)\
- [kaelzhang/node-ignore](https://github.com/kaelzhang/node-ignore)

## .gitignore pattern reference:

These examples assume you created a new repository at `c:\projects\cat_translator`

## Special Characters

character | description
----------|------------
lines starting with '#' | this is a comment, git ignores these lines
`*` | matches **everything except** `/`
`?` | matches a single character that is **anything except** `/`
lines starting with '!' | they negate a pattern, including instead of ignoring
`/` | directory or path separator
lines ending with `/` | only matches directories
`[ac]` | matches the letter `a` or `c`
`[a-f]` | matches any letter in the range: `a`, `b`, `c`, `d`, `e`, `f`
`[0-4]` | matches a number in the range `0`, `1`, `2`, `3`, `4`
`[a-zA-Z]` | matches any letter, capital or lowercase
`a/**/b` | matches **zero or more subdirectories** between `a` and `b`

`backup.zip` or `*.zip` are equivalent to `**/backup.zip` and `**/*.zip`
`a/**/b` matches `a/b`, `a/x/b`, `a/x/y/b`

## Ignoring filetypes for any directory

`*.zip`

## ignoring folders in any directory

`zipfiles/`

This excludes

- `c:\projects\cat_translator\zipfiles\`
- `c:\projects\cat_translator\images\zipfiles\`

## Ignoring files that begin with '2020' that are '.md' files

`2020*.md`

This excludes

- `c:\projects\cat_translator\2020-summary.md`
- `c:\projects\cat_translator\backup\2020-summary.md`
- `c:\projects\cat_translator\backup\2020.jpg.md`

This allows

- `c:\projects\cat_translator\2019-summary.md`
- `c:\projects\cat_translator\backup\20191132134.md`
- `c:\projects\cat_translator\2020.md.jpg`

## Ignoring folders only in the base directory

`/zipfiles`

This excludes

- `c:\projects\cat_translator\zipfiles\`

This allows

- `c:\projects\cat_translator\images\zipfiles`

## ignore everything in a specific directory, without testing deeper files

`/backups/*`

This excludes

- `c:\projects\cat_translator\backups\another_folder` a folder in `backups`
- `c:\projects\cat_translator\backups\backup.zip` a file in `backups`

This allows

- `c:\projects\cat_translator\backups\another_folder\backup.zip` 

Files and folders past the first depth are allowed. 
This is because `*` does not match slashes `/` which means folders

`data/*.zip` cannot match `data/archive/backup.zip`

use `data/**/*.zip` if you want to ignore zero or more child folders of `data/`

## Allow zips in the base directory, but ignore everywhere else

`/*/*.zip`

This excludes

- `c:\projects\cat_translator\images\backup.zip`
- `c:\projects\cat_translator\logs\2020\backup.zip`

This allows

- `c:\projects\cat_translator\backup.zip`


## references 

- [.gitignore syntax : official docs](https://git-scm.com/docs/gitignore)
