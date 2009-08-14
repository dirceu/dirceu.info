task :default => "site:generate"

namespace :site do
  task :generate do
    `jekyll --permalink "/:title"`
  end
end