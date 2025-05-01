# Alle Pfade von http://api.heal.htb/download?filename=../../

---

# Useful:

## /config/boot.rb -> Dadurch geschaut, was die Gemfile genau ist -> Gemfile.lock
```
ENV["BUNDLE_GEMFILE"] ||= File.expand_path("../Gemfile", __dir__)

require "bundler/setup" # Set up gems listed in the Gemfile.
require "bootsnap/setup" # Speed up boot time by caching expensive operations.
```

## /Gemfile.lock
Infos:
- Gemfile.lock -> Alle Dependencies mit Version
```
GEM
  remote: https://rubygems.org/
  specs:
    actioncable (7.1.4)
      actionpack (= 7.1.4)
      activesupport (= 7.1.4)
      nio4r (~> 2.0)
      websocket-driver (>= 0.6.1)
      zeitwerk (~> 2.6)
    actionmailbox (7.1.4)
      actionpack (= 7.1.4)
      activejob (= 7.1.4)
      activerecord (= 7.1.4)
      activestorage (= 7.1.4)
      activesupport (= 7.1.4)
      mail (>= 2.7.1)
      net-imap
      net-pop
      net-smtp
    actionmailer (7.1.4)
      actionpack (= 7.1.4)
      actionview (= 7.1.4)
      activejob (= 7.1.4)
      activesupport (= 7.1.4)
      mail (~> 2.5, >= 2.5.4)
      net-imap
      net-pop
      net-smtp
      rails-dom-testing (~> 2.2)
    actionpack (7.1.4)
      actionview (= 7.1.4)
      activesupport (= 7.1.4)
      nokogiri (>= 1.8.5)
      racc
      rack (>= 2.2.4)
      rack-session (>= 1.0.1)
      rack-test (>= 0.6.3)
      rails-dom-testing (~> 2.2)
      rails-html-sanitizer (~> 1.6)
    actiontext (7.1.4)
      actionpack (= 7.1.4)
      activerecord (= 7.1.4)
      activestorage (= 7.1.4)
      activesupport (= 7.1.4)
      globalid (>= 0.6.0)
      nokogiri (>= 1.8.5)
    actionview (7.1.4)
      activesupport (= 7.1.4)
      builder (~> 3.1)
      erubi (~> 1.11)
      rails-dom-testing (~> 2.2)
      rails-html-sanitizer (~> 1.6)
    activejob (7.1.4)
      activesupport (= 7.1.4)
      globalid (>= 0.3.6)
    activemodel (7.1.4)
      activesupport (= 7.1.4)
    activerecord (7.1.4)
      activemodel (= 7.1.4)
      activesupport (= 7.1.4)
      timeout (>= 0.4.0)
    activestorage (7.1.4)
      actionpack (= 7.1.4)
      activejob (= 7.1.4)
      activerecord (= 7.1.4)
      activesupport (= 7.1.4)
      marcel (~> 1.0)
    activesupport (7.1.4)
      base64
      bigdecimal
      concurrent-ruby (~> 1.0, >= 1.0.2)
      connection_pool (>= 2.2.5)
      drb
      i18n (>= 1.6, < 2)
      minitest (>= 5.1)
      mutex_m
      tzinfo (~> 2.0)
    base64 (0.2.0)
    bcrypt (3.1.20)
    bigdecimal (3.1.8)
    bootsnap (1.18.4)
      msgpack (~> 1.2)
    builder (3.3.0)
    concurrent-ruby (1.3.4)
    connection_pool (2.4.1)
    crass (1.0.6)
    date (3.3.4)
    debug (1.9.2)
      irb (~> 1.10)
      reline (>= 0.3.8)
    drb (2.2.1)
    erubi (1.13.0)
    globalid (1.2.1)
      activesupport (>= 6.1)
    i18n (1.14.6)
      concurrent-ruby (~> 1.0)
    imgkit (1.6.3)
    io-console (0.7.2)
    irb (1.14.1)
      rdoc (>= 4.0.0)
      reline (>= 0.4.2)
    jwt (2.9.1)
      base64
    loofah (2.22.0)
      crass (~> 1.0.2)
      nokogiri (>= 1.12.0)
    mail (2.8.1)
      mini_mime (>= 0.1.1)
      net-imap
      net-pop
      net-smtp
    marcel (1.0.4)
    mini_mime (1.1.5)
    minitest (5.25.1)
    msgpack (1.7.2)
    mutex_m (0.2.0)
    net-imap (0.4.16)
      date
      net-protocol
    net-pop (0.1.2)
      net-protocol
    net-protocol (0.2.2)
      timeout
    net-smtp (0.5.0)
      net-protocol
    nio4r (2.7.3)
    nokogiri (1.16.7-aarch64-linux)
      racc (~> 1.4)
    nokogiri (1.16.7-arm-linux)
      racc (~> 1.4)
    nokogiri (1.16.7-arm64-darwin)
      racc (~> 1.4)
    nokogiri (1.16.7-x86-linux)
      racc (~> 1.4)
    nokogiri (1.16.7-x86_64-darwin)
      racc (~> 1.4)
    nokogiri (1.16.7-x86_64-linux)
      racc (~> 1.4)
    psych (5.1.2)
      stringio
    puma (6.4.3)
      nio4r (~> 2.0)
    racc (1.8.1)
    rack (3.1.7)
    rack-cors (2.0.2)
      rack (>= 2.0.0)
    rack-session (2.0.0)
      rack (>= 3.0.0)
    rack-test (2.1.0)
      rack (>= 1.3)
    rackup (2.1.0)
      rack (>= 3)
      webrick (~> 1.8)
    rails (7.1.4)
      actioncable (= 7.1.4)
      actionmailbox (= 7.1.4)
      actionmailer (= 7.1.4)
      actionpack (= 7.1.4)
      actiontext (= 7.1.4)
      actionview (= 7.1.4)
      activejob (= 7.1.4)
      activemodel (= 7.1.4)
      activerecord (= 7.1.4)
      activestorage (= 7.1.4)
      activesupport (= 7.1.4)
      bundler (>= 1.15.0)
      railties (= 7.1.4)
    rails-dom-testing (2.2.0)
      activesupport (>= 5.0.0)
      minitest
      nokogiri (>= 1.6)
    rails-html-sanitizer (1.6.0)
      loofah (~> 2.21)
      nokogiri (~> 1.14)
    railties (7.1.4)
      actionpack (= 7.1.4)
      activesupport (= 7.1.4)
      irb
      rackup (>= 1.0.0)
      rake (>= 12.2)
      thor (~> 1.0, >= 1.2.2)
      zeitwerk (~> 2.6)
    rake (13.2.1)
    rdoc (6.7.0)
      psych (>= 4.0.0)
    reline (0.5.10)
      io-console (~> 0.5)
    rexml (3.3.7)
    sqlite3 (1.7.3-aarch64-linux)
    sqlite3 (1.7.3-arm-linux)
    sqlite3 (1.7.3-arm64-darwin)
    sqlite3 (1.7.3-x86-linux)
    sqlite3 (1.7.3-x86_64-darwin)
    sqlite3 (1.7.3-x86_64-linux)
    stringio (3.1.1)
    thor (1.3.2)
    timeout (0.4.1)
    tzinfo (2.0.6)
      concurrent-ruby (~> 1.0)
    webrick (1.8.2)
    websocket-driver (0.7.6)
      websocket-extensions (>= 0.1.0)
    websocket-extensions (0.1.5)
    zeitwerk (2.6.18)

PLATFORMS
  aarch64-linux
  arm-linux
  arm64-darwin
  x86-linux
  x86_64-darwin
  x86_64-linux

DEPENDENCIES
  bcrypt (~> 3.1.7)
  bootsnap
  debug
  imgkit
  jwt
  puma (>= 5.0)
  rack-cors
  rails (~> 7.1.3, >= 7.1.3.4)
  rexml
  sqlite3 (~> 1.4)
  tzinfo-data

RUBY VERSION
   ruby 3.3.5p100

BUNDLED WITH
   2.5.20
```

## /config/database.yml -> Dadurch die DB gefunden ```storage/development.sqlite3```
Infos:
- SQLite Version 3.8.0
- Dev + Production DB: ```storage/development.sqlite3```
- Test DB: ```storage/test.sqlite3```
```
# SQLite. Versions 3.8.0 and up are supported.
#   gem install sqlite3
#
#   Ensure the SQLite 3 gem is defined in your Gemfile
#   gem "sqlite3"
#
default: &default
  adapter: sqlite3
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  timeout: 5000

development:
  <<: *default
  database: storage/development.sqlite3

# Warning: The database defined as "test" will be erased and
# re-generated from your development database when you run "rake".
# Do not set this db to the same as development or production.
test:
  <<: *default
  database: storage/test.sqlite3

production:
  <<: *default
  database: storage/development.sqlite3
```

## /storage/development.sqlite3
Infos:
- Datenbank binary


## /config/credentials.yml.enc
```
1dMkoxx+3u+vK2g1BWntnRZqGj16vLi5rQJlP/P+pcIpGeK7b12TC2UWjrdx+PoC3iYnMWS2QLK5jnBnaNXDHpEL9oDgc6Ul/9/ghl+3g4AzaFeHy1/yG6SMxA11CMmQhTcSGj1jBMyCT7dgmV6/hfCyb933QHukceAV1NVHqLH9Tcd+WnB3okQhD3NUOLhZ3ivc3wr2pyvxX7ym5kLIjSuHNwRcmMwcXS3e26Bc3Lk9ghUq795a90WfGtV7cIa2TzdY5lbMHHi167IP3zzpUvmY0AcR+WmXHt35WjktrELPe7hR83MRHwTrWt3OmqafsPBufCl1oUY1K2sEIJ8VQjHhrP870ASSS3BpEiGSdrCU53jNVIquJwaE8lg0p3phhMbLXYVVT9QZO1banDh5avfcmSEM--dsbT6QUqCzyNMigC--9SEHtK8HjvpnlvfmWIqoMg==
```

## /log/development.log
```
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.2ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.0ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.0ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.0ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.2ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.0ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.0ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.3ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.0ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.2ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.3ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.0ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.2ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.2ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.0ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.2ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.2ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.1ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.2ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.2ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.2ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Load (0.2ms)[0m  [1m[34mSELECT "users".* FROM "users" WHERE "users"."username" = ? AND "users"."fullname" = ? AND "users"."email" = ? LIMIT ?[0m  [["username", "ralph"], ["fullname", "Administrator"], ["email", "ralph@heal.htb"], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:4:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mbegin transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."email" = ? AND "users"."id" != ? LIMIT ?[0m  [["email", "ralph@heal.htb"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mUser Exists? (0.1ms)[0m  [1m[34mSELECT 1 AS one FROM "users" WHERE "users"."username" = ? AND "users"."id" != ? LIMIT ?[0m  [["username", "ralph"], ["id", 1], ["LIMIT", 1]]
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'
  [1m[36mTRANSACTION (0.1ms)[0m  [1m[36mcommit transaction[0m
  ↳ lib/tasks/create_or_update_admin.rake:7:in `block (2 levels) in <main>'

```
---



---
# Not useful atm:

## /config/environments/test.rb
```
require "active_support/core_ext/integer/time"

# The test environment is used exclusively to run your application's
# test suite. You never need to work with it otherwise. Remember that
# your test database is "scratch space" for the test suite and is wiped
# and recreated between test runs. Don't rely on the data there!

Rails.application.configure do
  # Settings specified here will take precedence over those in config/application.rb.

  # While tests run files are not watched, reloading is not necessary.
  config.enable_reloading = false

  # Eager loading loads your entire application. When running a single test locally,
  # this is usually not necessary, and can slow down your test suite. However, it's
  # recommended that you enable it in continuous integration systems to ensure eager
  # loading is working properly before deploying your code.
  config.eager_load = ENV["CI"].present?

  # Configure public file server for tests with Cache-Control for performance.
  config.public_file_server.enabled = true
  config.public_file_server.headers = {
    "Cache-Control" => "public, max-age=#{1.hour.to_i}"
  }

  # Show full error reports and disable caching.
  config.consider_all_requests_local = true
  config.action_controller.perform_caching = false
  config.cache_store = :null_store

  # Render exception templates for rescuable exceptions and raise for other exceptions.
  config.action_dispatch.show_exceptions = :rescuable

  # Disable request forgery protection in test environment.
  config.action_controller.allow_forgery_protection = false

  # Store uploaded files on the local file system in a temporary directory.
  config.active_storage.service = :test

  config.action_mailer.perform_caching = false

  # Tell Action Mailer not to deliver emails to the real world.
  # The :test delivery method accumulates sent emails in the
  # ActionMailer::Base.deliveries array.
  config.action_mailer.delivery_method = :test

  # Print deprecation notices to the stderr.
  config.active_support.deprecation = :stderr

  # Raise exceptions for disallowed deprecations.
  config.active_support.disallowed_deprecation = :raise

  # Tell Active Support which deprecation messages to disallow.
  config.active_support.disallowed_deprecation_warnings = []

  # Raises error for missing translations.
  # config.i18n.raise_on_missing_translations = true

  # Annotate rendered view with file names.
  # config.action_view.annotate_rendered_view_with_filenames = true

  # Raise error when a before_action's only/except options reference missing actions
  config.action_controller.raise_on_missing_callback_actions = true
end
```

## /config/initializers/filter_parameter_logging.rb
```
# Be sure to restart your server when you modify this file.

# Configure parameters to be partially matched (e.g. passw matches password) and filtered from the log file.
# Use this to limit dissemination of sensitive information.
# See the ActiveSupport::ParameterFilter documentation for supported notations and behaviors.
Rails.application.config.filter_parameters += [
  :passw, :secret, :token, :_key, :crypt, :salt, :certificate, :otp, :ssn
]
```

## /config/initializers/cors.rb
```
# Be sure to restart your server when you modify this file.

# Avoid CORS issues when API is called from the frontend app.
# Handle Cross-Origin Resource Sharing (CORS) in order to accept cross-origin Ajax requests.

# Read more: https://github.com/cyu/rack-cors

Rails.application.config.middleware.insert_before 0, Rack::Cors do
  allow do
    origins "heal.htb", "api.heal.htb"

    resource "*",
      headers: :any,
      methods: [:get, :post, :put, :patch, :delete, :options, :head]
  end
end
```

## /config/cable.yml
```
development:
  adapter: async

test:
  adapter: test

production:
  adapter: redis
  url: <%= ENV.fetch("REDIS_URL") { "redis://localhost:6379/1" } %>
  channel_prefix: resume_api_production
```

## /app/models/user.rb
```
class User < ApplicationRecord
  before_create :set_default_admin

  
  has_secure_password
  validates :email, presence: true, uniqueness: true
  validates :username, presence: true, uniqueness: true
  validates :fullname, presence: true

  private

  def set_default_admin
    self.is_admin = false if is_admin.nil?
  end
end
```

## /app/controllers/application_controller.rb
```
class ApplicationController < ActionController::API
end
```

## /config/environments/development.rb
```
require "active_support/core_ext/integer/time"

Rails.application.configure do
  # Settings specified here will take precedence over those in config/application.rb.

  # In the development environment your application's code is reloaded any time
  # it changes. This slows down response time but is perfect for development
  # since you don't have to restart the web server when you make code changes.
  config.enable_reloading = true

  # Do not eager load code on boot.
  config.eager_load = false
  
  config.hosts << "api.heal.htb"

  # Show full error reports.
  config.consider_all_requests_local = true

  # Enable server timing
  config.server_timing = true

  # Enable/disable caching. By default caching is disabled.
  # Run rails dev:cache to toggle caching.
  if Rails.root.join("tmp/caching-dev.txt").exist?
    config.cache_store = :memory_store
    config.public_file_server.headers = {
      "Cache-Control" => "public, max-age=#{2.days.to_i}"
    }
  else
    config.action_controller.perform_caching = false

    config.cache_store = :null_store
  end

  # Store uploaded files on the local file system (see config/storage.yml for options).
  config.active_storage.service = :local

  # Don't care if the mailer can't send.
  config.action_mailer.raise_delivery_errors = false

  config.action_mailer.perform_caching = false

  # Print deprecation notices to the Rails logger.
  config.active_support.deprecation = :log

  # Raise exceptions for disallowed deprecations.
  config.active_support.disallowed_deprecation = :raise

  # Tell Active Support which deprecation messages to disallow.
  config.active_support.disallowed_deprecation_warnings = []

  # Raise an error on page load if there are pending migrations.
  config.active_record.migration_error = :page_load

  # Highlight code that triggered database queries in logs.
  config.active_record.verbose_query_logs = true

  # Highlight code that enqueued background job in logs.
  config.active_job.verbose_enqueue_logs = true


  # Raises error for missing translations.
  # config.i18n.raise_on_missing_translations = true

  # Annotate rendered view with file names.
  # config.action_view.annotate_rendered_view_with_filenames = true

  # Uncomment if you wish to allow Action Cable access from any origin.
  # config.action_cable.disable_request_forgery_protection = true

  # Raise error when a before_action's only/except options reference missing actions
  config.action_controller.raise_on_missing_callback_actions = true
end
```

## /config/environments/production.rb
```
require "active_support/core_ext/integer/time"

Rails.application.configure do
  # Settings specified here will take precedence over those in config/application.rb.

  # Code is not reloaded between requests.
  config.enable_reloading = false

  # Eager load code on boot. This eager loads most of Rails and
  # your application in memory, allowing both threaded web servers
  # and those relying on copy on write to perform better.
  # Rake tasks automatically ignore this option for performance.
  config.eager_load = true
  config.hosts << "api.heal.htb"
  # Full error reports are disabled and caching is turned on.
  config.consider_all_requests_local = false

  # Ensures that a master key has been made available in ENV["RAILS_MASTER_KEY"], config/master.key, or an environment
  # key such as  This key is used to decrypt credentials (and other encrypted files).
  # config.require_master_key = true

  # Disable serving static files from `public/`, relying on NGINX/Apache to do so instead.
  # config.public_file_server.enabled = false

  # Enable serving of images, stylesheets, and JavaScripts from an asset server.
  # config.asset_host = "http://assets.example.com"

  # Specifies the header that your server uses for sending files.
  # config.action_dispatch.x_sendfile_header = "X-Sendfile" # for Apache
  # config.action_dispatch.x_sendfile_header = "X-Accel-Redirect" # for NGINX

  # Store uploaded files on the local file system (see config/storage.yml for options).
  config.active_storage.service = :local

  # Mount Action Cable outside main process or domain.
  # config.action_cable.mount_path = nil
  # config.action_cable.url = "wss://example.com/cable"
  # config.action_cable.allowed_request_origins = [ "http://example.com", /http:\/\/example.*/ ]

  # Assume all access to the app is happening through a SSL-terminating reverse proxy.
  # Can be used together with config.force_ssl for Strict-Transport-Security and secure cookies.
  # config.assume_ssl = true

  # Force all access to the app over SSL, use Strict-Transport-Security, and use secure cookies.
  config.force_ssl = false

  # Log to STDOUT by default
  config.logger = ActiveSupport::Logger.new(STDOUT)
    .tap  { |logger| logger.formatter = ::Logger::Formatter.new }
    .then { |logger| ActiveSupport::TaggedLogging.new(logger) }

  # Prepend all log lines with the following tags.
  config.log_tags = [ :request_id ]

  # "info" includes generic and useful information about system operation, but avoids logging too much
  # information to avoid inadvertent exposure of personally identifiable information (PII). If you
  # want to log everything, set the level to "debug".
  config.log_level = ENV.fetch("RAILS_LOG_LEVEL", "info")

  # Use a different cache store in production.
  # config.cache_store = :mem_cache_store

  # Use a real queuing backend for Active Job (and separate queues per environment).
  # config.active_job.queue_adapter = :resque
  # config.active_job.queue_name_prefix = "resume_api_production"

  config.action_mailer.perform_caching = false

  # Ignore bad email addresses and do not raise email delivery errors.
  # Set this to true and configure the email server for immediate delivery to raise delivery errors.
  # config.action_mailer.raise_delivery_errors = false

  # Enable locale fallbacks for I18n (makes lookups for any locale fall back to
  # the I18n.default_locale when a translation cannot be found).
  config.i18n.fallbacks = true

  # Don't log any deprecations.
  config.active_support.report_deprecations = false

  # Do not dump schema after migrations.
  config.active_record.dump_schema_after_migration = false

  # Enable DNS rebinding protection and other `Host` header attacks.
  # config.hosts = [
  #   "example.com",     # Allow requests from example.com
  #   /.*\.example\.com/ # Allow requests from subdomains like `www.example.com`
  # ]
  # Skip DNS rebinding protection for the default health check endpoint.
  # config.host_authorization = { exclude: ->(request) { request.path == "/up" } }
end
```

## /config/application.rb
```
require_relative "boot"

require "rails/all"

# Require the gems listed in Gemfile, including any gems
# you've limited to :test, :development, or :production.
Bundler.require(*Rails.groups)

module ResumeApi
  class Application < Rails::Application
    # Initialize configuration defaults for originally generated Rails version.
    config.load_defaults 7.1

    # Please, add to the `ignore` list any other `lib` subdirectories that do
    # not contain `.rb` files, or that should not be reloaded or eager loaded.
    # Common ones are `templates`, `generators`, or `middleware`, for example.
    config.autoload_lib(ignore: %w(assets tasks))

    # Configuration for the application, engines, and railties goes here.
    #
    # These settings can be overridden in specific environments using the files
    # in config/environments, which are processed later.
    #
    # config.time_zone = "Central Time (US & Canada)"
    # config.eager_load_paths << Rails.root.join("extras")

    # Only loads a smaller set of middleware suitable for API only apps.
    # Middleware like session, flash, cookies can be added back manually.
    # Skip views, helpers and assets when generating a new resource.
    config.api_only = true
  end
end
```

## /config/routes.rb
```
Rails.application.routes.draw do
  get '/', to: 'rails/welcome#index'
  post 'signup', to: 'authentication#signup'
  post 'signin', to: 'authentication#signin'
  get 'profile', to: 'authentication#profile'
  get 'resume', to: 'authentication#resume'
  delete 'logout', to: 'authentication#logout'
  post 'exports', to: 'exports#create'
  get 'download', to: 'exports#download'
end
```

## /config/puma.rb
```
# This configuration file will be evaluated by Puma. The top-level methods that
# are invoked here are part of Puma's configuration DSL. For more information
# about methods provided by the DSL, see https://puma.io/puma/Puma/DSL.html.

# Puma can serve each request in a thread from an internal thread pool.
# The `threads` method setting takes two numbers: a minimum and maximum.
# Any libraries that use thread pools should be configured to match
# the maximum value specified for Puma. Default is set to 5 threads for minimum
# and maximum; this matches the default thread size of Active Record.
max_threads_count = ENV.fetch("RAILS_MAX_THREADS") { 5 }
min_threads_count = ENV.fetch("RAILS_MIN_THREADS") { max_threads_count }
threads min_threads_count, max_threads_count

# Specifies that the worker count should equal the number of processors in production.
if ENV["RAILS_ENV"] == "production"
  require "concurrent-ruby"
  worker_count = Integer(ENV.fetch("WEB_CONCURRENCY") { Concurrent.physical_processor_count })
  workers worker_count if worker_count > 1
end

# Specifies the `worker_timeout` threshold that Puma will use to wait before
# terminating a worker in development environments.
worker_timeout 3600 if ENV.fetch("RAILS_ENV", "development") == "development"

# Specifies the `port` that Puma will listen on to receive requests; default is 3000.
port ENV.fetch("PORT") { 3000 }

# Specifies the `environment` that Puma will run in.
environment ENV.fetch("RAILS_ENV") { "development" }

# Specifies the `pidfile` that Puma will use.
pidfile ENV.fetch("PIDFILE") { "tmp/pids/server.pid" }

# Allow puma to be restarted by `bin/rails restart` command.
plugin :tmp_restart
```
---
