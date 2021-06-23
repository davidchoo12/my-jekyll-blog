# My personal blog made using Jekyll

To test new post:
- write the md file in `_posts`, filename has to be in format of `yyyy-mm-dd-title.md` where title doesn't matter whether space or hyphen seperated
- run `bundle exec jekyll serve --force_polling -I -l`
  - `--force_polling` cos it is a mounted dir in WSL2 (see [issue](https://github.com/microsoft/WSL/issues/216#issuecomment-626327824))
  - `-I` for incremental, faster build, good for when editting post. Remove this flag if need to clean rebuild, eg after removing date prefix of a post filename, the post disappears in the posts page, then renaming it back with date prefix still doesn't show up cos of this flag.
  - `-l` for live reload browser on build
- open `localhost:4000`

Uses Ruby version 2.7.2, just ignore all the deprecation warnings. There was something that prevented using Ruby 3 but I forgot what.

Files in `_posts` need to have date prefix, doesn't matter what date but I use the date I start writing the file. Reason is described [here](https://stackoverflow.com/questions/27099427/jekyll-filename-without-date). Without date prefix, jekyll cannot find the file and return 404. Alternatively, can another collections like what I did for `_pages`, maybe name it `_articles`, then all posts can put in that folder without needing the date prefix.