require 'rake-jekyll'

# This task builds the Jekyll site and deploys it to a remote Git repository.
# It's preconfigured to be used with GitHub and Travis CI.
# See http://github.com/jirutka/rake-jekyll for more options.
Rake::Jekyll::GitDeployTask.new(:deploy) do |t|

  # Description of the rake task.
 t.description = 'Generate the site and push changes to remote repository'

 # Overrides the *author* of the commit being created with author of the
 # source commit (i.e. HEAD in the current branch).
 t.author = -> {
   `git log -n 1 --format='%aN <%aE>'`.strip
 }
 # Overrides the *author date* of the commit being created with date of the
 # source commit.
 t.author_date = -> {
   `git log -n 1 --format='%aD'`.strip
 }
 # The commit message will contain hash of the source commit.
 t.commit_message = -> {
   "Built from #{`git rev-parse --short HEAD`.strip}"
 }
