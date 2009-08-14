load 'deploy' if respond_to?(:namespace) # cap2 differentiator
 
set :application, "blog"
set :domain, "slicehost"
set :repository, "git@github.com:dirceu/dirceu.info.git"
set :use_sudo, false
set :deploy_to, "/var/www/dirceu.info/#{application}"
ssh_options[:forward_agent] = true
default_run_options[:pty] = true
 
role :app, domain
role :web, domain
set :scm, :git
set :deploy_via, :remote_cache 
default_run_options[:pty] = true
 
namespace :deploy do
  task :restart, :roles => :app do
  end
 
  task :start, :roles => :app do
    # nothing
  end
 
  task :stop, :roles => :app do
    # nothing
  end
  
  task :finalize_update do
    # nothing
  end
end
 
namespace :jekyll do
  desc "Generates the site on the remote server"
  task :generate_site do
    run "cd #{current_release} && /var/lib/gems/1.8/bin/rake site:generate"
  end
end
 
after "deploy:update_code", "jekyll:generate_site"