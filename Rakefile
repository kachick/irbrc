# frozen_string_literal: true

require('rake/testtask')

begin
  require('rubocop/rake_task')
rescue LoadError
  puts('can not use rubocop in this environment')
else
  RuboCop::RakeTask.new
end

task(default: [:rubocop])

# desc('Simulate CI results in local machine as possible')
# multitask(simulate_ci: [:test, :rubocop])

# Rake::TestTask.new(:test) do |tt|
#   tt.pattern = 'test/**/test_*.rb'
#   tt.warning = true
# end

desc 'Print dependencies'
task :deps do
  sh('ruby --version')
  sh('dprint --version')
  sh('typos --version')
end

desc 'Tests except ruby'
task :check_non_ruby do
  sh('typos . .github .vscode')
  sh('dprint check')
  sh('nixpkgs-fmt --check ./*.nix')
end
