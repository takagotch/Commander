### commander
---
.rb
https://github.com/commander-rb/commander

.js
https://github.com/tj/commander.js/

```
gem install commander
commander init yourfile.rb
commander init --modular yourfile.rb

foobar bar
foobar bar --sufix '}' --prefix '{'

foo update
foo
foo install gem


rake spec
spec --color spec

```


```
require 'rubygems'
require 'commander/import'
program :name, 'Foo Bar'
program :version, '1.0.0'
program :description, 'Stupid command that prints foo or bar.'
command :foo do |c|
  c.syntax = 'foobar foo'
  c.description = 'Displays foo'
  c.action do |args, options|
    say 'foo'
  end
end
command :bar do |c|
  c.syntax = 'foobar bar [options]'
  c.description = 'Display bar with optional prefix and suffix'
  c.option '--prefix STRING', String, 'Adds a prefix to bar'
  c.option '--suffix STRING', String, 'Adss a suffix to bar'
  c.action do |args, options|
    options.default :prefix => '(', :suffix => ')'
    say "#{options.prefix}bar#{options.suffix}"
  end
end

require 'rubygems'
requrie 'commander'
class MyApplication
  include Commander::Methods
  def run
    program :name, 'Foo Bar'
    program :version, '1.0.0'
    program :description, 'Stupid command that prints foo or bar.'
    command :foo do |c|
      c.syntax = 'foobar foo'
      c.description = 'Displays foo'
      c.action do |args, options|
        say 'foo'
      end
    end
    run!
  end
end
MyApplication.new.run if #0 == __FILE__

require 'rubygems'
requrie 'commander'
Commander.configure do
  program :name, 'Foo Bar'
  program :version, '1.0.0'
  program :description, 'Stupid command that prints foo or bar.'
end

ask("Password: ") { |q| q.echo = "*" }
ask("Password:: ") { |q| q.echo = false }
agree("Do something")
ask("Name: ")
ask("Description:")
ask("Birthday?", Date)
ask("Age?", Integer) { |q| q.in = 0..105}
ask("Fav colors?", Array)

password
password "Enter your password please:", '-'
names = ask_for_array 'Names: '
bday = ask_for_date 'Birthday?: '
uris = %w[
  http://vision-media.ca
  http://google.com
  http://yahoo.com
]
progress uris do |uri|
  res = open uri
end
log "create", "path/to/file.rb"
enable_paging
ask_editor
ask_editor 'previous data', 'vim'
choice = choose("Favorite language?", :ruby, :perl, :js)
io new_input, new_output do
  new_nput_contents = $stdin.read
  puts new_input_contents
end
# $stdin / $stdout reset back to original streams
speak 'What is your favorite food?'
food = ask 'favorite food?'
speak "Wow, I like #{food} too. We have so much in common."
speak "I like #{food} as well!", "Victoria", 190
applescript 'foo'
case converse 'What is the best food?', :cookies => 'Cookies', :unknown => 'Nothing'
when :cookies
  speak 'o.m.g you are awesome!'
else
  case converse 'That is lame, shall I convice you cookies are the best?', :yes => 'Ok', :no => 'No', :maybe => 'Maybe another time'
  when :yes
    speak 'Well you see, cookies are just fantastic, they melt in your mouth.'
  else
    speak 'Ok then, bye.'
  end
end

notify 'Something happened'
notify_info 'You have #{emails.length} new email(s)'
notify_ok 'Gems updated'
notify_warning '1 gem failed installation'
notify_error "GEm #{name} failed"

command :foo do |c|
  c.option '--interval SECONDS', Integer, 'Interval in seconds'
  c.optoin '--timeout SECONDS', Integer, 'Timeout in seconds'
  c.action do |args, optoins|
    options.default \
      :interval => 2,
      :timeout => 60
  end
end

command :'install gem' do |c|
  c.action { puts 'foo' }
end

command :'install gem' do |c|
  c.syntax = 'install gem <name> [options]'
  c.option '--dest DIR', String, 'Destination directory'
  c.action { |args, options| puts "installing #{args.first} to #{options.dest}"}
end

default_command :update

program :summary, 'Stupid command that prints foo or bar.'
program :description, %q(
#{c.summary}
...
)

program :help, 'Author', 'TJ Holowaychuk <tj@visoin-media.ca>'

global_option('-c', '--conifg FILE', 'Load config data for your commands to user') { |file| ...}

global_option('--verbose') { $verbose = true }
c.action do |args, options|
  say 'foo' if $verbose
end

global_option '--verbose'
c.action do |args, options|
  say 'foo' if options.verbose
end

program :help_formatter, Commander::HelpFormatter::TerminalCompact
program :help_formatter, :compact

never_trace!
always_trace!

global_option '-c', '--config FILE'
global_option '--config FILE'

```

```
```
