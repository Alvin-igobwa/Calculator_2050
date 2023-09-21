require 'ffi'

this_directory = File.dirname(__FILE__)

COMPILER = 'gcc'
COMPILE_FLAGS = '-fPIC'
SHARED_LIBRARY_FLAGS = '-shared -fPIC'

OUTPUT = FFI.map_library_name 'excelspreadsheet'
OUTPUT_DIR = this_directory
SOURCE = 'excelspreadsheet.c'
OBJECT = 'excelspreadsheet.o'

task :default => [:build]

desc 'Build the 2050 model, then install it'
task :build => [OUTPUT]

file OUTPUT => OBJECT do
  puts "Turning #{OBJECT} and putting it in #{OUTPUT_DIR} as #{OUTPUT}"
  puts "Note that this is a really large c file, it may take tens of minutes to compile."
  sh "#{COMPILER} #{SHARED_LIBRARY_FLAGS} -o #{File.join(OUTPUT_DIR,OUTPUT)} #{OBJECT}"
end

file OBJECT => SOURCE do
  puts "Building #{SOURCE}"
  puts "Note that this is a really large c file, it may take tens of minutes to compile."
  sh "#{COMPILER} #{COMPILE_FLAGS} -o #{OBJECT} -c #{SOURCE}"
end
