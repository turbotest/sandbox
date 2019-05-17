require "rake/testtask"
require 'erb'
require 'yaml'
require 'securerandom'
require 'fileutils'

task default: %i[ test ]

Rake::TestTask.new do |t|
  t.libs << "test"
  t.test_files = FileList['test/*_test.rb']
  t.verbose = true
end

desc "Generate test files with discourse durations"
task :generate_files do
  template = ERB.new File.read('template_test.erb')
  profile = YAML.load_file 'test_suite.yml'
  FileUtils.mkdir_p 'test'

  profile['lines_per_file'].each do |line_count|
    uid = SecureRandom.uuid.gsub /-/, '_'

    @test_class = 'DiscourseTest'
    @test_name  = uid
    @duration   = line_count * profile['mean_test_seconds']
    @pass       = true

    File.write "test/#{ uid }_test.rb", template.result(binding)
  end
end
