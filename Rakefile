
task :proto do

  gopath = ENV["GOPATH"]
  if gopath.nil?
    puts "GOPATH not set."
    exit 1
  end

  # Now run the generation command

  packages = ["src/client/pfs/pfs.proto"]
  root = "#{gopath}/src/github.com/pachyderm/pachyderm"
  packages.each do |package|
    system "protoc --ruby_out=lib/proto -I #{root} #{root}/#{package}"
  end

end


task :install_pach_dependencies do
  #TODO - check if go installed
  #TODO - check if already in gopath

  puts "Installing pachyderm library"
  system %x`go get github.com/pachyderm/pachyderm/src/client`

end
