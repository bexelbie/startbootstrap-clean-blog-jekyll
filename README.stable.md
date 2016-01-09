A "stablized" branch of [startbootstrap-clean-blog-jekyll](https://github.com/IronSummitMedia/startbootstrap-clean-blog-jekyll) for use as an update merge to update my blog site.

Confused? You should probably read the [README for the base theme](README.theme.md)

# How to use this branch

## Upgrading (may be out of date - sorry)

1. `git remote add upstream git@github.com:BlackrockDigital/startbootstrap-clean-blog-jekyll.git`
1. `git fetch upstream'
1. `git checkout master` This should be in upstream only
1. `git merge upstream/master'
1. `git checkout stable`
1. `git rebase -i master` and resolve conflicts and make decisions:


    1. `git status`
    2. Look for lines like this, if any:

      ~~~
Changes to be committed:

    new file:   CHANGES_IN_THIS_BRANCH.md
      ~~~

      These files are not necessarily wanted, so if you don't want them remember to delete them.

    3. Resolve conflicts using standard git procedures.

      * This is going to suck for some files.
      * I am sorry.
      * Suggestions welcome.
      * If you bias toward the incoming changes where they represent rearrangement of lines and other non-consequential changes you may be happier during future merges.
      * You may want to clone this repo somewhere to wholesale copy files out of for things like bootstrap.css where you are likely to accept all changes.
      * Refactoring any of your customer CSS out of the provided theme CSS files will make this easier

## Recommended usage testing with the official Jekyll Docker Container

    $ docker run -e BUNDLE_CACHE=1 --rm --label=jekyll --volume=$(pwd):/srv/jekyll -it -p $(boot2docker ip):4000:4000 jekyll/jekyll jekyll s --force_polling

  Note: `sudo` may be needed depending on your setup


## If you are not using the official Jekyll Docker Container

If you are not using the official jekyll docker container, it is probably safe to delete the following from Gemfile

    jekyll-watch

You can also delete the following from the .gitignore

    vendor
    .bundle

## To upgrade your blog

1. `git remote add theme git@github.com:bexelbie/startbootstrap-clean-blog-jekyll.git`
1. `git fetch theme`
1. `git checkout stable` - should get this branch into your repo
1. `git rebase -i master` - and pray

HAHAHAH nope - do it by hand fool!


# Changes in this Branch

## The following PRs have been merged into this branch, prior to their merge by upstream

The full change log is below.

# Maintenance

1. git remote add upstream git@github.com:BlackrockDigital/startbootstrap-clean-blog-jekyll.git
2. git checkout gh-pages
3. git merge upstream/gh-pages
4. git push origin gh-pages
5. git checkout stable
6. git rebase -i gh-pages

## Change Log

Sat Sep 10 16:44:08 UTC 2016
  * refactored the LinkedIn patch and resubmitted it to upstream
  * added categories, tags and navigation

Sat May 21 20:53:43 CEST 2016:
  * Updated code from upstream
  * Only 1 PR and the private data, container, and README changes is still needed

Sat Jan  9 15:46:39 CET 2016:

  * Merged upstream PRs ahead of upstream
    * PR 62 merged
    * PR 67 merged
    * PR 77 merged
    * PR 79 merged
    * PR 80 merged
  * Added Gemfile and updated .gitignore for use with the Jekyll Docker Container
  * Deleted sample data that is unneeded when doing a theme upgrade
    * _posts/2014-06-10-dinosaurs.markdown
    * _posts/2014-07-01-dreams.markdown
    * _posts/2014-07-08-failure-is-not-an-option.markdown
    * _posts/2014-08-24-science-has-not-yet-mastered-prophecy.markdown
    * _posts/2014-09-18-i-believe.markdown
    * _posts/2014-09-24-man-must-explore.markdown
    * about.html
    * contact.html
    * img/about-bg.jpg
    * img/contact-bg.jpg
    * img/home-bg.jpg
    * img/post-bg-01.jpg
    * img/post-bg-02.jpg
    * img/post-bg-03.jpg
    * img/post-bg-04.jpg
    * img/post-bg-05.jpg
    * img/post-bg-06.jpg
    * img/post-sample-image.jpg
  * Fixed typo in PR 67 - LinkedIn Footer
    * https://github.com/IronSummitMedia/startbootstrap-clean-blog-jekyll/pull/67/files#r49265217
  * Re-Merged PR 80 - for updated with {% feed_meta %}
