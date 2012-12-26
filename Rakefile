task :default => 'install_dotfile'
task :install_dotfile do
 
  files = Dir['*'] - %w[Rakefile ssh] 
  files.each do |file|
    puts "install #{file}"
    system %Q{rm -rf $HOME/.#{file}}
    system %Q{cp #{file} $HOME/.#{file}}
  end
 
  puts "install ssh config"
  system %Q{mkdir -p $HOME/.ssh/}
  system %Q{cp ssh/config $HOME/.ssh/}

  system %Q{git config --global core.editor "vim"}
end
