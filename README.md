# kevinashworth.com

I build [my website](http://kevinashworth.com/) with this code. It uses [Jekyll](https://github.com/jekyll/jekyll) and [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) (both offer MIT Licenses), and I deploy it on AWS S3 using [s3_website](https://github.com/laurilehmijoki/s3_website). All my original content is copyrighted — but mostly I only care about anything that rhymes.

## Commands 2022-11-07

After adding fork of s3_website to Gemfile

```zsh
bundle install
bundle exec jekyll serve
JEKYLL_ENV="production" bundle exec jekyll build
bundle exec s3_website push --dry-run
bundle exec s3_website push
```
