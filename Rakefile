require 'rubygems'
require 'rake'

TOP_DIR = File.expand_path(File.join(File.dirname(__FILE__)))
BUILD_DIR = File.expand_path(File.join(File.dirname(__FILE__), "build"))
BUILD_ID = ENV.has_key?("BUILD_ID") ? ENV["BUILD_ID"] : 1

task :default do
  sh("mkdir -p #{BUILD_DIR}/usr/bin")
  sh("cp #{TOP_DIR}/fantastic.sh #{BUILD_DIR}/usr/bin")
  sh("chmod 755 #{BUILD_DIR}/usr/bin/fantastic.sh")
  sh("fpm -s dir -t rpm -n fantastic -v #{BUILD_ID} -C #{BUILD_DIR} usr/bin/fantastic.sh")
  sh("fpm -s dir -t deb -n fantastic -v #{BUILD_ID} -C #{BUILD_DIR} usr/bin/fantastic.sh")
end
