RIAK_VERSION            = "2.0.0pre11"
RIAK_DOWNLOAD_URL       = "http://s3.amazonaws.com/downloads.basho.com/riak/2.0/2.0.0pre11/osx/10.8/riak-2.0.0pre11-OSX-x86_64.tar.gz"

# The number of riak nodes to start (1-5, default: 3)
#
# If you increase the number for an existing cluster, use
#
#   $ rake bootstrap
#
# afterwards to install and join the additional nodes.
#
NUM_NODES = 5

task :default => :help

task :help do
  sh %{rake -T}
end

desc "install riak"
task :install => [:fetch_riak, :copy_riak]

task :fetch_riak do
  sh "curl -L #{RIAK_DOWNLOAD_URL} | tar xz -" unless File.exist? "riak-#{RIAK_VERSION}"
end

task :copy_riak do
  (1..NUM_NODES).each do |n|
    system %{cp -nr riak-#{RIAK_VERSION}/ dev#{n}}
  end
end