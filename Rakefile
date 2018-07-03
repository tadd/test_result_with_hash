require 'erb'

def erb(source_file, dest_file, vars = {})
  applied = ERB.new(File.read(source_file)).result_with_hash(vars)
  File.write(dest_file, applied)
end

default: :index

file 'public/index.txt' do |t|
  Dir.mkdir 'public' unless Dir.exist?('public')
  erb('index.txt.erb', 'public/index.txt', value: world)
end
