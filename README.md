#Publishing System Documentation

First up, if you would like to add to this documentation, GitHub uses [Markdown](https://daringfireball.net/projects/markdown/) and here's a great 3 minute [GitHub guide](https://guides.github.com/features/mastering-markdown/) on mastering markdown.  The best practice way to add to this documenatation is to [fork](https://help.github.com/articles/fork-a-repo/) and create a [pull request](https://help.github.com/articles/creating-a-pull-request/). The easiest way to start using GitHub is to use [GitHub Desktop](https://desktop.github.com/).

We are looking to use the containerization technology [Docker](https://www.docker.com/) and maybe [Vagrant](https://www.vagrantup.com/). This project is primarily using Ruby so have a quick read of the results from the [2016 Rails Survey](http://rails-hosting.com/2016/index.html).

- [Company Website](#company-website)
- [Publishing System Hosting Options](#publishing-system-hosting-options)
- [Highly sought after skills](#highly-sought-after-skills)
- [Interesting Skills](#interesting-skills)
- [Oracle VM VirtualBox](#oracle-vm-virtualbox)
- [Windows](#windows)
  - [Git](#git)
  - [Ruby](#ruby)
    - [hashcheck.rb](#the-first-ruby-tool)
  - [JRuby](#jruby)
  - [Jekyll](#jekyll)
- [XSLT XPath resouces](#xslt-xpath-resources)
- [Important Reading](#important-reading)
- [Programming Editors](#programming-editors)
- [Helpful links](#helpful-links)
- [Free online interactive easy quick courses](#free-online-interactive-easy-quick-courses)        
- [Essential Programmer Training](#essential-programmer-training)   

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Company website

- [GitHub Pages](https://pages.github.com/)
- [Jekyll](https://jekyllrb.com/)
- [kramdown](http://kramdown.gettalong.org/)
- [Sass](http://sass-lang.com/)
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [HTML 5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
- [CSS 3](https://developer.mozilla.org/en/docs/Web/CSS/CSS3)
- [typer.js](http://steven.codes/typerjs/)
- [Google Charts](https://developers.google.com/chart/)

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Task to do after you first join GitHub

##Follow all these people

- [The Real Beast](https://github.com/jbampton)
- [Preston Hunter](https://github.com/prestonhunter)
- [Linus Torvalds](https://github.com/torvalds)
- [Jose Valim](https://github.com/josevalim)
- [Nobuyoshi Nakada](https://github.com/nobu)
- [Yukihiro "Matz" Matsumoto](https://github.com/matz)

##Star and Watch some projects

- [The Real Beast](https://github.com/jbampton/jbampton.github.io)
- [Linux](https://github.com/torvalds/linux)
- [Ruby](https://github.com/ruby/ruby)
- [Phalcon Framework](https://github.com/phalcon/cphalcon)
- [Laravel](https://github.com/laravel/laravel)
- [Rails](https://github.com/rails/rails)
- [Foundation](https://github.com/zurb/foundation-sites)
- [Jekyll](https://github.com/jekyll/jekyll)
- [kramdown](https://github.com/gettalong/kramdown)
- [Sass](https://github.com/sass/sass)
                      
[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Publishing System Hosting Options

- [Heroku](https://www.heroku.com/)
- [Engine Yard](https://www.engineyard.com/)

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Highly sought after skills

- [Ruby on Rails](http://rubyonrails.org/)
- [Ubuntu](https://www.ubuntu.com/)
- [Prawn PDF](https://github.com/prawnpdf/prawn)
- [Prawn Table](https://github.com/prawnpdf/prawn-table)
- [The Ruby Toolbox - PDF Generation](https://www.ruby-toolbox.com/categories/pdf_generation)
- [The Rails Command Line](http://guides.rubyonrails.org/command_line.html)
- [Oracle VM VirtualBox](https://www.virtualbox.org/)

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Interesting Skills
- [Nokogiri](http://www.nokogiri.org/)
- [Ruby Saxon::Xslt](https://github.com/fidothe/saxon-xslt)
- [SAXON The XSLT and XQuery Processor](http://saxon.sourceforge.net/)
- [Saxonica](http://www.saxonica.com/welcome/welcome.xml)
- [Apache FOP](https://xmlgraphics.apache.org/fop/)
- [JRuby](http://jruby.org/) 

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Oracle VM VirtualBox

This section is dedicated to those that run Mac OS or Windows that need to run Ubuntu with [Oracle VM VirtualBox](https://www.virtualbox.org/).  Here is in depth [documentation](https://www.virtualbox.org/manual/ch01.html) on how to get VirtualBox running.

###Host machine

####Minimum host requirements

16GB RAM, [Octa-core](https://en.wikipedia.org/wiki/Microprocessor) desktop class CPU, [64 Bit](https://en.wikipedia.org/wiki/64-bit_computing) OS

###Guest VM - Ubuntu

####Minimun VM requirements

8GB RAM, Quad Core CPU.

More to come soon.

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Windows

##Git

This project is using [Git](https://git-scm.com/) and GitHub.  The easiest way to get started with GitHub is to use [GitHub Desktop](https://desktop.github.com/).  Below shows how to get help on the **git** command:

```
PS C:\Users\beast> git --help
usage: git [--version] [--help] [-C <path>] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone      Clone a repository into a new directory
   init       Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add        Add file contents to the index
   mv         Move or rename a file, a directory, or a symlink
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect     Use binary search to find the commit that introduced a bug
   grep       Print lines matching a pattern
   log        Show commit logs
   show       Show various types of objects
   status     Show the working tree status

grow, mark and tweak your common history
   branch     List, create, or delete branches
   checkout   Switch branches or restore working tree files
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   merge      Join two or more development histories together
   rebase     Reapply commits on top of another base tip
   tag        Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch      Download objects and refs from another repository
   pull       Fetch from and integrate with another repository or a local branch
   push       Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
PS C:\Users\beast>
```

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


##Ruby

Using [Ruby](https://www.ruby-lang.org/en/) (a programmer's best friend) we can harness the power of [RubyGems](https://rubygems.org/).  

If you're on Windows and you want to try Ruby quickly try the Ruby Installer and you will need to install the Ruby DevKit if you want to use native gems.
- [RubyInstaller](http://rubyinstaller.org/)
- [Ruby DevKit](http://rubyinstaller.org/add-ons/devkit/)

Make sure to download the RubyInstaller from JFrog Bintray [here]( https://bintray.com/oneclick/rubyinstaller/rubyinstaller/2.3.1) and make sure to get the highest Ruby version which is currently version [2.3.1](https://www.ruby-lang.org/en/news/2016/04/26/ruby-2-3-1-released/).  You can also find the [Ruby DevKit on JFrog Bintary](https://bintray.com/oneclick/rubyinstaller/DevKit/view).

Before using the both the RubyInstaller and the Ruby DevKit you should check the [integrity](https://en.wikipedia.org/wiki/File_verification) of them with the **CertUtil** command and compare your command line console ouput with what is displayed on the JFrog website. The  **CertUtil** command is shown below:

```
CertUtil -hashfile pathToFileToCheck [HashAlgorithm]
```

[HashAlgorithm](https://en.wikipedia.org/wiki/Secure_Hash_Algorithm) choices: MD2 MD4 MD5 SHA1 SHA256 SHA384 SHA512

An example of checking the RubyInstaller checksum with the **CertUtil** command is show below as well as running [irb](http://ruby-doc.org/stdlib-2.0.0/libdoc/irb/rdoc/IRB.html) to remove the single spaces between each set of two characters:
```
PS C:\Users\beast\Downloads> CertUtil -hashfile .\rubyinstaller-2.3.1-x64.exe SHA256
SHA256 hash of file .\rubyinstaller-2.3.1-x64.exe:
a8 83 e2 4b 9a 2b 38 31 70 e1 7c 37 2c ec 32 bd eb 28 04 eb c1 ca 59 97 d6 8d 97 cd dd ae 88 3c
CertUtil: -hashfile command completed successfully.
PS C:\Users\beast\Downloads> irb
irb(main):001:0> "a8 83 e2 4b 9a 2b 38 31 70 e1 7c 37 2c ec 32 bd eb 28 04 eb c1 ca 59 97 d6 8d 97 cd dd ae 88 3c".split
.join
=> "a883e24b9a2b383170e17c372cec32bdeb2804ebc1ca5997d68d97cdddae883c"
irb(main):002:0>

```

###The first Ruby Tool

**hashcheck.rb** is a Ruby based command line program that checks file checksums and runs as shown below:
```
PS C:\Users\john\Downloads> ruby .\hashcheck.rb .\rubyinstaller-2.3.1-x64.exe SHA256
a883e24b9a2b383170e17c372cec32bdeb2804ebc1ca5997d68d97cdddae883c
PS C:\Users\john\Downloads>
```

**hashcheck.rb** is shown below:

```ruby
#ARGV[0] is the file you want to check. ARGV[1] is the hash algorithm
#Secure_Hash_Algorithm choices: MD2 MD4 MD5 SHA1 SHA256 SHA384 SHA512
shellcommand = `CertUtil -hashfile "#{ARGV[0]}" "#{ARGV[1]}"`
puts shellcommand.inspect.split('\n')[1].split.join
```

More infomation on the **CertUtil** command is shown below:

```
C:\Users\beast\Downloads>CertUtil -?

Verbs:
  -dump             -- Dump configuration information or files
  -asn              -- Parse ASN.1 file

  -decodehex        -- Decode hexadecimal-encoded file
  -decode           -- Decode Base64-encoded file
  -encode           -- Encode file to Base64

  -deny             -- Deny pending request
  -resubmit         -- Resubmit pending request
  -setattributes    -- Set attributes for pending request
  -setextension     -- Set extension for pending request
  -revoke           -- Revoke Certificate
  -isvalid          -- Display current certificate disposition

  -getconfig        -- Get default configuration string
  -ping             -- Ping Active Directory Certificate Services Request interf
ace
  -pingadmin        -- Ping Active Directory Certificate Services Admin interfac
e
  -CAInfo           -- Display CA Information
  -ca.cert          -- Retrieve the CA's certificate
  -ca.chain         -- Retrieve the CA's certificate chain
  -GetCRL           -- Get CRL
  -CRL              -- Publish new CRLs [or delta CRLs only]
  -shutdown         -- Shutdown Active Directory Certificate Services

  -installCert      -- Install Certification Authority certificate
  -renewCert        -- Renew Certification Authority certificate

  -schema           -- Dump Certificate Schema
  -view             -- Dump Certificate View
  -db               -- Dump Raw Database
  -deleterow        -- Delete server database row

  -backup           -- Backup Active Directory Certificate Services
  -backupDB         -- Backup Active Directory Certificate Services database
  -backupKey        -- Backup Active Directory Certificate Services certificate
and private key
  -restore          -- Restore Active Directory Certificate Services
  -restoreDB        -- Restore Active Directory Certificate Services database
  -restoreKey       -- Restore Active Directory Certificate Services certificate
 and private key
  -importPFX        -- Import certificate and private key
  -dynamicfilelist  -- Display dynamic file List
  -databaselocations -- Display database locations
  -hashfile         -- Generate and display cryptographic hash over a file

  -store            -- Dump certificate store
  -addstore         -- Add certificate to store
  -delstore         -- Delete certificate from store
  -verifystore      -- Verify certificate in store
  -repairstore      -- Repair key association or update certificate properties o
r key security descriptor
  -viewstore        -- Dump certificate store
  -viewdelstore     -- Delete certificate from store

  -dsPublish        -- Publish certificate or CRL to Active Directory

  -ADTemplate       -- Display AD templates
  -Template         -- Display Enrollment Policy templates
  -TemplateCAs      -- Display CAs for template
  -CATemplates      -- Display templates for CA
  -enrollmentServerURL -- Display, add or delete enrollment server URLs associat
ed with a CA
  -ADCA             -- Display AD CAs
  -CA               -- Display Enrollment Policy CAs
  -Policy           -- Display Enrollment Policy
  -PolicyCache      -- Display or delete Enrollment Policy Cache entries
  -CredStore        -- Display, add or delete Credential Store entries
  -InstallDefaultTemplates -- Install default certificate templates
  -URLCache         -- Display or delete URL cache entries
  -pulse            -- Pulse autoenrollment events
  -MachineInfo      -- Display Active Directory machine object information
  -DCInfo           -- Display domain controller information
  -EntInfo          -- Display enterprise information
  -TCAInfo          -- Display CA information
  -SCInfo           -- Display smart card information

  -SCRoots          -- Manage smart card root certificates

  -verifykeys       -- Verify public/private key set
  -verify           -- Verify certificate, CRL or chain
  -syncWithWU       -- Sync with Windows Update
  -generateSSTFromWU -- Generate SST from Windows Update
  -sign             -- Re-sign CRL or certificate

  -vroot            -- Create/delete web virtual roots and file shares
  -vocsproot        -- Create/delete web virtual roots for OCSP web proxy
  -addEnrollmentServer -- Add an Enrollment Server application
  -deleteEnrollmentServer -- Delete an Enrollment Server application
  -oid              -- Display ObjectId or set display name
  -error            -- Display error code message text
  -getreg           -- Display registry value
  -setreg           -- Set registry value
  -delreg           -- Delete registry value

  -ImportKMS        -- Import user keys and certificates into server database fo
r key archival
  -ImportCert       -- Import a certificate file into the database
  -GetKey           -- Retrieve archived private key recovery blob
  -RecoverKey       -- Recover archived private key
  -MergePFX         -- Merge PFX files
  -ConvertEPF       -- Convert PFX files to EPF file
  -?                -- Display this usage message


CertUtil -?              -- Display a verb list (command list)
CertUtil -dump -?        -- Display help text for the "dump" verb
CertUtil -v -?           -- Display all help text for all verbs

CertUtil: -? command completed successfully.

C:\Users\beast\Downloads>
```

There has been a recent update to RubyGems and you might not be able to install any remote gems without first downloading and installing the [RubyGems update](https://rubygems.org/pages/download) manually as seen below:

```
PS C:\Users\beast\Downloads\rubygems-2.6.8> ruby setup.rb
RubyGems 2.6.8 installed
Parsing documentation for rubygems-2.6.8
Installing ri documentation for rubygems-2.6.8
...
```

You can also use the unsupported [Microsoft File Checksum Integrity Verifier](http://www.microsoft.com/en-au/download/details.aspx?id=11533) to check some types of file checksums.  Make sure you keep the Microsoft File Checksum Integrity Verifier in your Windows "Downloads" folder, so you can use it check all your downloads that have checksums.

The **RubyInstaller** is a Windows executable program with a GUI so it is easy to install.  To install the **Ruby DevKit** you need to 'cd' to where you extracted the **Ruby DevKit** and run the commnads shown below:

```
PS C:\> cd Devkit
PS C:\Devkit> ruby dk.rb init
[INFO] found RubyInstaller v2.3.1 at C:/Ruby23-x64

Initialization complete! Please review and modify the auto-generated
'config.yml' file to ensure it contains the root directories to all
of the installed Rubies you want enhanced by the DevKit.

PS C:\Devkit> ruby dk.rb install
[INFO] Installing 'C:/Ruby23-x64/lib/ruby/site_ruby/2.3.0/rubygems/defaults/operating_system.rb'
[INFO] Installing 'C:/Ruby23-x64/lib/ruby/site_ruby/devkit.rb'
PS C:\Devkit>
```

The commands above are explained in more detail on the [GitHub Ruby DevKit page](https://github.com/oneclick/rubyinstaller/wiki/Development-Kit).  When I installed Ruby last it was installed in: 'C:\Ruby23-x64' and that was for Ruby 2.3.1. After you have installed Ruby you can check it's installed by running the next command:

```
PS C:\> ruby -v
ruby 2.3.1p112 (2016-04-26 revision 54768) [x64-mingw32]
PS C:\>
```
You can find about more about the installled Ruby by typing the next command:
```
PS C:\> ruby -h
Usage: C:\Ruby23-x64\bin\ruby.exe [switches] [--] [programfile] [arguments]
  -0[octal]       specify record separator (\0, if no argument)
  -a              autosplit mode with -n or -p (splits $_ into $F)
  -c              check syntax only
  -Cdirectory     cd to directory before executing your script
  -d              set debugging flags (set $DEBUG to true)
  -e 'command'    one line of script. Several -e's allowed. Omit [programfile]
  -Eex[:in]       specify the default external and internal character encodings
  -Fpattern       split() pattern for autosplit (-a)
  -i[extension]   edit ARGV files in place (make backup if extension supplied)
  -Idirectory     specify $LOAD_PATH directory (may be used more than once)
  -l              enable line ending processing
  -n              assume 'while gets(); ... end' loop around your script
  -p              assume loop like -n but print line also like sed
  -rlibrary       require the library before executing your script
  -s              enable some switch parsing for switches after script name
  -S              look for the script using PATH environment variable
  -T[level=1]     turn on tainting checks
  -v              print version number, then turn on verbose mode
  -w              turn warnings on for your script
  -W[level=2]     set warning level; 0=silence, 1=medium, 2=verbose
  -x[directory]   strip off text before #!ruby line and perhaps cd to directory
  -h              show this message, --help for more info
PS C:\>
```


Once you have installed Ruby you will have to get used to using the [gem command](http://guides.rubygems.org/rubygems-basics/).  Help on the gem command is shown below:
```
C:\>gem -h
RubyGems is a sophisticated package manager for Ruby.  This is a
basic help message containing pointers to more information.

  Usage:
    gem -h/--help
    gem -v/--version
    gem command [arguments...] [options...]

  Examples:
    gem install rake
    gem list --local
    gem build package.gemspec
    gem help install

  Further help:
    gem help commands            list all 'gem' commands
    gem help examples            show some examples of usage
    gem help gem_dependencies    gem dependencies file guide
    gem help platforms           gem platforms guide
    gem help <COMMAND>           show help on COMMAND
                                   (e.g. 'gem help install')
    gem server                   present a web page at
                                 http://localhost:8808/
                                 with info about installed gems
  Further information:
    http://guides.rubygems.org
```

You can use the **gem list** command to list your installed local gems as seen below:
```
C:\>gem list

*** LOCAL GEMS ***

activesupport (5.0.0, 4.2.6)
addressable (2.4.0)
ast (2.3.0)
bigdecimal (1.2.7, 1.2.6)
bundler (1.12.5)
coffee-script (2.4.1)
coffee-script-source (1.10.0)
colorator (1.1.0, 0.1)
concurrent-ruby (1.0.2)
ethon (0.9.0)
execjs (2.7.0)
faraday (0.9.2)
ffi (1.9.14 x64-mingw32, 1.9.13 x64-mingw32)
fileutils (0.7)
gemoji (2.1.0)
github-pages (87, 86)
github-pages-health-check (1.1.2, 1.1.0)
googlecharts (1.6.12)
html-pipeline (2.4.2, 2.4.1)
i18n (0.7.0)
io-console (0.4.6, 0.4.3)
jekyll (3.1.6)
jekyll-coffeescript (1.0.1)
jekyll-feed (0.6.0, 0.5.1)
jekyll-gist (1.4.0)
jekyll-github-metadata (2.0.2)
jekyll-mentions (1.1.3)
jekyll-paginate (1.1.0)
jekyll-redirect-from (0.11.0, 0.10.0)
jekyll-sass-converter (1.4.0, 1.3.0)
jekyll-seo-tag (2.0.0)
jekyll-sitemap (0.11.0, 0.10.0)
jekyll-watch (1.4.0)
jemoji (0.7.0, 0.6.2)
json (2.0.1, 1.8.3, 1.8.1)
kramdown (1.11.1)
liquid (3.0.6)
listen (3.1.5, 3.0.6)
mercenary (0.3.6)
mini_portile2 (2.1.0)
minitest (5.9.0, 5.4.3)
multipart-post (2.0.0)
net-dns (0.8.0)
nokogiri (1.6.8 x64-mingw32)
ocra (1.3.6)
octokit (4.3.0)
parser (2.3.1.4, 2.3.1.2)
pdf-core (0.6.1)
pkg-config (1.1.7)
power_assert (0.3.0, 0.2.2)
powerpack (0.1.1)
prawn (2.1.0)
psych (2.1.0, 2.0.8)
public_suffix (2.0.2, 1.5.3)
rainbow (2.1.0)
rake (10.4.2)
rb-fsevent (0.9.7)
rb-inotify (0.9.7)
rdoc (4.2.0)
rmagick (2.15.4)
rouge (1.11.1)
rubocop (0.43.0, 0.41.2)
ruby-progressbar (1.8.1)
ruby_dep (1.3.1)
safe_yaml (1.0.4)
sass (3.4.22)
sawyer (0.7.0)
terminal-table (1.6.0)
test-unit (3.0.8)
thread_safe (0.3.5)
ttfunk (1.4.0)
typhoeus (0.8.0)
tzinfo (1.2.2)
unicode-display_width (1.1.1, 1.1.0)
wdm (0.1.1)
```
Another way to see more information on the installed RubyGems on your system is bring up the **gem server** locally hosted webpage as seen below:
```
PS C:\Users\beast> gem server
Server started at http://[::]:8808
Server started at http://0.0.0.0:8808
127.0.0.1 - - [12/Nov/2016:07:56:55 E. Australia Standard Time] "GET / HTTP/1.1" 200 56728
- -> /
127.0.0.1 - - [12/Nov/2016:07:56:55 E. Australia Standard Time] "GET /gem-server-rdoc-style.css HTTP/1.1" 200 4313
http://127.0.0.1:8808/ -> /gem-server-rdoc-style.css
127.0.0.1 - - [12/Nov/2016:07:56:55 E. Australia Standard Time] "GET /favicon.ico HTTP/1.1" 404 281
http://127.0.0.1:8808/ -> /favicon.ico
```

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


##JRuby

[JRuby](http://jruby.org/) requires [Java](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) to be installed and the current version for Windows is Java 111. You can use the following command to see if Java is installed on your machine:

```
C:\>java -version
java version "1.8.0_111"
Java(TM) SE Runtime Environment (build 1.8.0_111-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.111-b14, mixed mode)

C:\>
```
Once you install JRuby you can check it's installed by running the next command:

```
C:\>jruby -v
jruby 9.1.5.0 (2.3.1) 2016-09-07 036ce39 Java HotSpot(TM) 64-Bit Server VM 25.10
1-b13 on 1.8.0_101-b13 +jit [mswin32-x86_64]

C:\>
```
You can find out more about JRuby by running the next command:
```

C:\>jruby -h
Usage: jruby [switches] [--] [programfile] [arguments]
  -0[octal]         specify record separator (\0, if no argument)
  -a                autosplit mode with -n or -p (splits $_ into $F)
  -c                check syntax only
  -Cdirectory       cd to directory, before executing your script
  -d                set debugging flags (set $DEBUG to true)
  -e 'command'      one line of script. Several -e's allowed. Omit [programfile]

  -Eex[:in]         specify the default external and internal character encoding
s
  -Fpattern         split() pattern for autosplit (-a)
  -G                load a Bundler Gemspec before executing any user code
  -i[extension]     edit ARGV files in place (make backup if extension supplied)

  -Idirectory       specify $LOAD_PATH directory (may be used more than once)
  -J[java option]   pass an option on to the JVM (e.g. -J-Xmx512m)
                      use --properties to list JRuby properties
                      run 'java -help' for a list of other Java options
  -l                enable line ending processing
  -n                assume 'while gets(); ... end' loop around your script
  -p                assume loop like -n but print line also like sed
  -rlibrary         require the library, before executing your script
  -s                enable some switch parsing for switches after script name
  -S                look for the script in bin or using PATH environment variabl
e
  -T[level]         turn on tainting checks
  -U                use UTF-8 as default internal encoding
  -v                print version number, then turn on verbose mode
  -w                turn warnings on for your script
  -W[level]         set warning level; 0=silence, 1=medium, 2=verbose (default)
  -x[directory]     strip off text before #!ruby line and perhaps cd to director
y
  -X[option]        enable extended option (omit option to list)
  -y                enable parsing debug output
  --copyright       print the copyright
  --debug           sets the execution mode most suitable for debugger
                      functionality
  --jdb             runs JRuby process under JDB
  --properties      List all configuration Java properties
                      (prepend "jruby." when passing directly to Java)
  --sample          run with profiling using the JVM's sampling profiler
  --profile         run with instrumented (timed) profiling, flat format
  --profile.api     activate Ruby profiler API
  --profile.flat    synonym for --profile
  --profile.graph   run with instrumented (timed) profiling, graph format
  --profile.html    run with instrumented (timed) profiling, graph format in HTM
L
  --profile.json    run with instrumented (timed) profiling, graph format in JSO
N
  --profile.out     [file]
  --profile.service <ProfilingService implementation classname>
                    output profile data to [file]
  --client          use the non-optimizing "client" JVM
                      (improves startup; default)
  --server          use the optimizing "server" JVM (improves perf)
  --headless        do not launch a GUI window, no matter what
  --dev             prioritize startup time over long term performance
  --manage          enable remote JMX management and monitoring of JVM and JRuby

  --bytecode        show the JVM bytecode produced by compiling specified code
  --version         print the version
  --disable-gems    do not load RubyGems on startup
  --enable=feature[,...], --disable=feature[,...]
                    enable or disable features
Features:
  gems                   rubygems (default: enabled)
  did_you_mean           did_you_mean (default: enabled)
  rubyopt                RUBYOPT environment variable (default: enabled)
  frozen-string-literal  freeze all string literals (default: disabled)

C:\>
```

You should check the JRuby **bin** folder as JRuby provides a JRuby version of most of all the standard Ruby commands and I installed JRuby at **C:\jruby-9.1.5.0\bin**.  You can use the **jgem** command to output a gem list and the gem list for a fresh JRuby install is shown below:

```
PS C:\> jgem list

*** LOCAL GEMS ***

did_you_mean (default: 1.0.1)
jar-dependencies (default: 0.3.5)
jruby-openssl (0.9.17 java)
jruby-win32ole (0.8.5)
json (1.8.3 java)
minitest (default: 5.4.1)
net-telnet (default: 0.1.1)
power_assert (default: 0.2.3)
psych (2.0.17 java)
racc (1.4.14 java)
rake (default: 10.4.2)
rdoc (default: 4.2.0)
test-unit (default: 3.1.1)
PS C:\>
```
JRuby also ships with **jirb** as seen below:
```
PS C:\> jirb
irb(main):001:0> 1+2
=> 3
irb(main):002:0> first ="john"
=> "john"
irb(main):003:0> last="Bampton"
=> "Bampton"
irb(main):004:0> "#{first} #{last}"
=> "john Bampton"
irb(main):005:0> (1..5) === 3
=> true
irb(main):006:0> exit
PS C:\>
```

##Jekyll

```
PS C:\work\github\jbampton.github.io> bundle exec jekyll serve
Configuration file: C:/work/github/jbampton.github.io/_config.yml
            Source: C:/work/github/jbampton.github.io
       Destination: C:/work/github/jbampton.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 1.18 seconds.
 Auto-regeneration: enabled for 'C:/work/github/jbampton.github.io'
Configuration file: C:/work/github/jbampton.github.io/_config.yml
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
      Regenerating: 1 file(s) changed at 2016-11-20 01:31:42 ...done in 15.700119 seconds.
      Regenerating: 1 file(s) changed at 2016-11-20 01:32:08 ...done in 0.56543 seconds.
```


[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#XSLT XPath resources

- [XPath Axes](http://www.w3schools.com/xml/xpath_axes.asp)
- [XSLT 2.0 and XPath 2.0 Programmer's Reference, 4th Edition](http://www.wrox.com/WileyCDA/WroxTitle/XSLT-2-0-and-XPath-2-0-Programmer-s-Reference-4th-Edition.productCd-0470192747.html) - John owns this large essential book from [Michael Kay](https://en.wikipedia.org/wiki/Michael_Howard_Kay)
- [XPath examples](https://msdn.microsoft.com/en-us/library/ms256086(v=vs.110).aspx)
- [XPath Wikipedia](https://en.wikipedia.org/wiki/XPath)

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)

#Important Reading

https://en.wikipedia.org/wiki/Technology_evangelist

https://www.fastcompany.com/3040723/12-signs-your-company-has-an-enviable-workplace-culture

http://www.tiobe.com/tiobe-index/

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Programming Editors

###Commercial

oXygen XML Editor - https://www.oxygenxml.com/

XMLSpy - alternative to oXygen XML - http://www.altova.com/xmlspy.html

Cross platform Linux, Mac, Windows Editor - Active State Komode IDE - http://komodoide.com/

Cross platform Linux, Mac, Windows - JetBrains RubyMine - The Most Intelligent Ruby and Rails IDE - https://www.jetbrains.com/ruby/

###Open Source

Cross platform Linux, Mac, Windows Editor - Active State Komode Edit - http://komodoide.com/komodo-edit/

Cross platform Linux, Mac, Windows Editor - Atom by GitHub - https://atom.io

Cross platform Linux, Mac, Windows Editor - https://www.sublimetext.com

Microsoft Visual Studio - https://www.visualstudio.com

Eclipse - https://eclipse.org/

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Helpful links

Creating and highlighting code blocks - https://help.github.com/articles/creating-and-highlighting-code-blocks/

Linguist langage extensions - https://github.com/github/linguist/blob/master/lib/linguist/languages.yml

How to check a file checksum - http://stackoverflow.com/questions/478722/what-is-the-best-way-to-calculate-a-checksum-for-a-file-that-is-on-my-machine

Mastering Markdown - https://guides.github.com/features/mastering-markdown/

Google Charts - https://developers.google.com/chart/

Ruby regular expression tester - http://rubular.com

RegExp tester, Open source languages - https://regex101.com

Emoji cheat sheet - http://www.webpagefx.com/tools/emoji-cheat-sheet/

[&#8595;](#essential-programmer-training) [&#8593;](#publishing-system-documentation)


#Free online interactive easy quick courses

###Learn Git

https://try.github.io/levels/1/challenges/1

https://www.codecademy.com/learn/learn-git

https://www.udacity.com/course/how-to-use-git-and-github--ud775

###Learn Ruby

http://tryruby.org/levels/1/challenges/0

https://www.codecademy.com/learn/ruby

https://www.codecademy.com/learn/learn-rails

###Learn Python

https://www.codecademy.com/learn/python

https://www.codeschool.com/courses/try-python

###Learn DevTools

http://discover-devtools.codeschool.com/

###Learn Web

https://www.codecademy.com/learn/learn-html-css

https://www.codecademy.com/learn/javascript

https://www.codecademy.com/learn/jquery

https://www.codecademy.com/learn/make-a-website

https://www.codecademy.com/en/skills/make-an-interactive-website

###Learn SQL

https://www.codecademy.com/learn/learn-sql

###Learn Miscellaneous

https://www.codecademy.com/learn/learn-the-command-line


#Essential Programmer Training

###Codewars

####Achieve mastery through challenge.  Improve your skills by training with others on real code challenges

http://www.codewars.com/

[&#8593;](#publishing-system-documentation)
