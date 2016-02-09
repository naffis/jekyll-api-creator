# Jekyll API builder

Create mock api's from pdf's and csv files using jekyll and github pages. Originally built for NARA's GRS team. 

To run the site locally:

    bundle exec jekyll serve

To build locally or to use Travis CI you'll have to modify your repository in the following way. From your project directory run the following:

    git init
    git remote add origin git@github.com:userName/repositoryName.git
    jekyll build
    git checkout master
    git add -A
    git commit -m "base source"
    git push origin master
    cd _site
    touch .nojekyll
    git init
    git remote add origin git@github.com:userName/repositoryName.git
    git checkout -b gh-pages
    git add -A
    git commit -m "first build"
    git push origin gh-pages

Note this process is for hosting on a project page. The process for hosting on a user or organization page is slightly different. 

Once you complete the steps above you can build locally and push to GitHub pages by running the following command:

    rake publish

To have Travis CI automatically publish your content to GitHub pages you'll need to complete the steps above and then modify your .travis.yml file and Rakefile accordingly. Once you've done that you can simply commit your changes to build and publish the content. 