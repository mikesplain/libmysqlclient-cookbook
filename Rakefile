require 'bundler/setup'

# Style tests. Rubocop and Foodcritic
namespace :style do
  require 'rubocop/rake_task'
  desc 'Run Ruby style checks'
  RuboCop::RakeTask.new(:ruby)

  require 'foodcritic'
  desc 'Run Chef style checks'
  FoodCritic::Rake::LintTask.new(:chef) do |t|
    t.options = {
      :fail_tags => ['any'],
      :tags => ['~FC005'],
    }
  end
end

desc 'Run all style checks'
task :style => ['style:chef', 'style:ruby']
