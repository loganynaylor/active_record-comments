require "bundler/setup"
require "bundler/gem_tasks"
require "bump/tasks"

task :spec do
  sh "rspec spec/"
end

task :default => :spec

desc "Bundle all gemfiles"
task :bundle_all do
  Bundler.with_original_env do
    system("which -s matching_bundle") || abort("gem install matching_bundle")
    Dir["gemfiles/*.gemfile"].each do |gemfile|
      sh "BUNDLE_GEMFILE=#{gemfile} matching_bundle"
    end
  end
end
