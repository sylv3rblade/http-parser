require 'rubygems'
require 'rake'
require 'rspec/core/rake_task'

task default: %i[compile test]

task :compile do
  protect = ['http_parser.c', 'http_parser.h']
  Dir['ext/http-parser/**/*'].each do |file|
    next if protect.include? File.basename(file)

    FileUtils.rm file
  rescue StandardError
  end
  system 'cd ext && rake'
end

RSpec::Core::RakeTask.new(:test)
