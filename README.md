=======
selenide-ru
===========

Selenide blog in Russian


### For developers:
sudo apt-get install ruby
sudo gem install jekyll bundler
bundle exec jekyll serve --watch --trace


### Release process
Just run script:
selenide> ./release 6.1.0

This script will:
1. add tag "v${version}"
2. build & run unit-tests
3. publish selenide-*jar to oss.sonatype.org
4. generate javadoc for site


### Ruby & Jekyll installation on Windows
1. Install Ruby
  http://rubyinstaller.org/downloads/
  Get version 1.9+, not 2.+

  Check:
```bash
c:\users\andrei>ruby -v
ruby 1.9.3p448 (2013-06-27) [i386-mingw32]
```

2. Download from `http://rubyinstaller.org/downloads/ file DevKit-tdm-32-*-sfx.exe`

   Unpack to any folder (NB! Do not use *~\Downloads*, but use e.g. *~\Downloads\temp_rubydevkit*)

   Follow installation instructions: https://github.com/oneclick/rubyinstaller/wiki/Development-Kit
```bash
   > ruby dk.rb init
   > ruby dk.rb install (NB! --force)
```

   Check:
```bash
     gem install json --platform=ruby
     ruby -rubygems -e "require 'json'; puts JSON.load('[42]').inspect"
```

3. Install Jekyll with dependencies:
```
   gem install github-pages
```

4. Run "jekyll build".

  Get error:
```
  Destination: D:/projects/selenide-web/_site
  Generating... D:/Ruby193/lib/ruby/gems/1.9.1/gems/posix-spawn-0.3.6/lib/posix/spawn.rb:162: warning: cannot close fd before spawn
  ←[31m  Conversion error: There was an error converting '_posts/2013-04-23-what-is-selenide.md'.←[0m
```

5. Google says: "Fix pygments gem version"
```
   gem uninstall pygments.rb --version "=0.5.2"
   gem install pygments.rb --version "=0.5.0"
```

6. Run `jekyll build`. Get error:
   Generating... ←[31m  Conversion error: There was an error converting '_posts/2013-04-23-what-is-selenide.md'.←[0m

7. Google says: "Install Python".

8. Install Python 2.+ (not 3.+) from http://www.python.org/getit/

9. Run `jekyll serve --watch`.

10. Open [http://localhost:4000](http://localhost:4000) in browser.


# Profit!
