require 'rake'
require 'yaml'
require 'time'
require "rubygems"

task :default => :build

/
    TODO's
      - Create a task to create a new page and post
 /

desc 'Preview blog on local machine'
task :preview => :clean do
    sh "bundle exec jekyll serve --watch --drafts --baseurl '' --config _config.yml"
end

desc 'Build static blog files'
task :build => :clean do
    sh "bundle exec jekyll build --incremental --config _config.yml"
end

desc 'Check configuration file for URL conflicts'
task :check do
    sh "jekyll doctor"
end

desc 'Clean up generated site'
task :clean do
    sh 'rm -rf _site'
end