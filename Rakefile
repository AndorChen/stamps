desc 'Preview locally'
task :server do
  system 'bundle exec jekyll server --force-polling'
end

desc 'Deploy to GitHub Pages'
task :deploy do
  puts 'Push to `master`'
  system "git push origin master"
  puts
  puts 'Push to `gh-pages`'
  system "bundle exec jekyll build"
  puts
  cd '_site' do
    system "git add -A"
    system "git commit -m 'update at #{Time.now.utc}'"
    puts
    system "git push origin gh-pages"
  end
end

task :default => :server
