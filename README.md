# Note to self

2018-06-13
I fixed an issue where localhost links got pushed to AWS by running this:

`JEKYLL_ENV="production" bundle exec jekyll build`

I'd forgotten to include the first part, and my site got borked for a while
