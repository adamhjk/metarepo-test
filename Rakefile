require 'rubygems'
require 'rake'

TOP_DIR = File.expand_path(File.join(File.dirname(__FILE__)))
BUILD_DIR = File.expand_path(File.join(File.dirname(__FILE__), "build"))
build_id = ENV.has_key?("BUILD_ID") ? ENV["BUILD_ID"].dup : "1"
build_id.gsub!('-', '')

task :default do
  sh("mkdir -p #{BUILD_DIR}/usr/bin")
  sh("cp #{TOP_DIR}/fantastic.sh #{BUILD_DIR}/usr/bin")
  sh("chmod 755 #{BUILD_DIR}/usr/bin/fantastic.sh")
  sh("fpm -s dir -t rpm -n fantastic -v #{build_id} -C #{BUILD_DIR} usr/bin/fantastic.sh")
  sh("fpm -s dir -t deb -n fantastic -v #{build_id} -C #{BUILD_DIR} usr/bin/fantastic.sh")
end
