require 'puppetlabs_spec_helper/rake_tasks'
require 'rspec/core/rake_task'

task :default => :unit

desc "Unit tests"
RSpec::Core::RakeTask.new(:unit) do |t,args|
  t.pattern     = 'spec/unit','spec/fixtures'
  t.rspec_opts  = '--color'
  t.verbose     = true
end

desc "Beaker namespace"
RSpec::Core::RakeTask.new('beaker:rspec:test:pe',:host) do |t,args|
  args.with_defaults({:host => 'default'})
  ENV['BEAKER_set'] = args[:host]
  t.pattern = 'spec/acceptance'
  t.rspec_opts = '--color'
  t.verbose = true
end
