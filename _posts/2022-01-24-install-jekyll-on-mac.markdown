---
layout: post
title: "Install Jekyll on Mac"
date: 2022-01-24 12:30:32 +0900
categories: jekyll update
---

ERROR: While executing gem ... (Errno::ENOTEMPTY)
Directory not empty @ dir_s_rmdir - /Users/spo/.rbenv/versions/3.0.0/lib/ruby/gems/3.0.0/gems/bundler-2.3.5

incompatible library version - /Users/spo/.gem/ruby/3.0.0/gems/ffi-1.15.5/lib/ffi_c.bundle (LoadError)
cannot load such file -- 3.0/ffi_c (LoadError)

$ gem pristine ffi
이걸로 안되면
$ gem uninstall ffi
$ gem install ffi

---

rbenv 설치 후

# Check your installation

curl -fsSL https://github.com/rbenv/rbenv-installer/raw/main/bin/rbenv-doctor | bash
설치 확인하면 아래의 에러가 날 때
The directory `/Users/spo/.rbenv/shims' must be present in PATH for rbenv to work.

해결법은
I added these lines at the end of my .zshrc file (for those of us who are using oh my zsh)

'# rbenv configuration

eval "$(rbenv init -)"
export RUBY_CONFIGURE_OPTS="--with-openssl-dir=$(brew --prefix openssl@1.1)"

터미널 재실행 필수

---

sudo gem install jekyll bundler

---

# Upgrade just RubyGems gems.

gem update --system

# Upgrade all global gems.

gem update
