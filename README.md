### cane
---
https://github.com/square/cane

```sh
gem install cane
cane --abc-glob '{lib,spec}/**/*.rb' --abc-max 15

cane

cane --help

cat .cane

cane

echo "89" > coverage/.last_run.json
cane --gte 'coverage/.last_json,90'

cane -r unhappy.rb --check UnhappyCheck --unhappy-file myfile

```

```ruby
begin
  require 'cane/rake_task'
  desc "Run cane to check quality metrics"
  Cane::RakeTask.new(:quality) do |cane|
    cane.abc_max = 10
    cane.add_threshold 'coverage/covered_percent', :>=, 99
    cane.no_style = true
    cane.abc_exclude = %w(Foo::Bar#some_method)
  end
  task :default => :quality
rescue LoadError
  warn "cane not available, quality task not provided."
end

```

```
```


