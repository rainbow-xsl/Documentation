#Publishing System Documentation
[&#8595;](#essential-programmer-training)

First up, if you would like to add to this documentation, GitHub uses [Markdown](https://daringfireball.net/projects/markdown/) and here's a great 3 minute [GitHub guide](https://guides.github.com/features/mastering-markdown/) on mastering markdown.  We are looking to use the containerization technology [Docker](https://www.docker.com/) and maybe [Vagrant](https://www.vagrantup.com/). This project is primarily using Ruby so have a quick read of the results from the [2016 Rails Survey](http://rails-hosting.com/2016/index.html).

##Company website

- [GitHub Pages](https://pages.github.com/)
- [Jekyll](https://jekyllrb.com/)
- [kramdown](http://kramdown.gettalong.org/)
- [Sass](http://sass-lang.com/)
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [HTML 5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
- [CSS 3](https://developer.mozilla.org/en/docs/Web/CSS/CSS3)
- [typer.js](http://steven.codes/typerjs/)
- [Google Charts](https://developers.google.com/chart/)


##Publishing System Hosting Options

- [Heroku](https://www.heroku.com/)
- [Engine Yard](https://www.engineyard.com/)


##Highly sought after skills

- [Ruby on Rails](http://rubyonrails.org/)
- [Ubuntu](https://www.ubuntu.com/)
- [Prawn PDF](https://github.com/prawnpdf/prawn)
- [The Ruby Toolbox - PDF Generation](https://www.ruby-toolbox.com/categories/pdf_generation)
- [The Rails Command Line](http://guides.rubyonrails.org/command_line.html)
- [Oracle VM VirtualBox](https://www.virtualbox.org/)


##Oracle VM VirtualBox

This section is dedicated to those that run Mac OS or Windows that need to run Ubuntu with [Oracle VM VirtualBox](https://www.virtualbox.org/).  Here is in depth [documentation](https://www.virtualbox.org/manual/ch01.html) on how to get VirtualBox running.

###Host machine

####Minimum host requirements

16GB RAM, [Octa-core](https://en.wikipedia.org/wiki/Microprocessor) desktop class CPU, [64 Bit](https://en.wikipedia.org/wiki/64-bit_computing) OS

###Guest VM - Ubuntu

####Minimun VM requirements

8GB RAM, Quad Core CPU.

More to come soon.


#Windows

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
In future another task is to create a Ruby script that calls the **CertUtil** command to automate this process. More infomation on the **CertUtil** command is shown below:

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



##XSLT XPath resources

- [XPath Axes](http://www.w3schools.com/xml/xpath_axes.asp)
- [XSLT 2.0 and XPath 2.0 Programmer's Reference, 4th Edition](http://www.wrox.com/WileyCDA/WroxTitle/XSLT-2-0-and-XPath-2-0-Programmer-s-Reference-4th-Edition.productCd-0470192747.html) - John owns this large essential book from [Michael Kay](https://en.wikipedia.org/wiki/Michael_Howard_Kay)
- [XPath examples](https://msdn.microsoft.com/en-us/library/ms256086(v=vs.110).aspx)
- [XPath Wikipedia](https://en.wikipedia.org/wiki/XPath)


##Helpful links

Creating and highlighting code blocks - https://help.github.com/articles/creating-and-highlighting-code-blocks/

Linguist langage extensions - https://github.com/github/linguist/blob/master/lib/linguist/languages.yml

How to check a file checksum - http://stackoverflow.com/questions/478722/what-is-the-best-way-to-calculate-a-checksum-for-a-file-that-is-on-my-machine

Mastering Markdown - https://guides.github.com/features/mastering-markdown/

Google Charts - https://developers.google.com/chart/

Ruby regular expression tester - http://rubular.com

RegExp tester, Open source languages - https://regex101.com

Emoji cheat sheet - http://www.webpagefx.com/tools/emoji-cheat-sheet/


##Free online interactive easy quick courses

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

###Learn Miscellaneous

https://www.codecademy.com/learn/learn-the-command-line


##Essential Programmer Training

###Codewars

####Achieve mastery through challenge.  Improve your skills by training with others on real code challenges

http://www.codewars.com/
