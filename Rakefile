task :default => "site:generate"

namespace :site do
  task :generate do
    `/var/lib/gems/1.8/bin/jekyll --permalink "/:title"`
  end
end