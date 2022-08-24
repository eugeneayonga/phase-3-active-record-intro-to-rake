# # Rakefile created at top of directory
# DEFINING TASKS
# task + task names as a symbol + code block

task :hello do
  # code block you want task to execute
  puts "hello from Rake!"
end




# Describing Tasks with rake -T
# view a list of available Rake tasks and their descriptions

desc 'outputs hola to the terminal'
task :hola do
  puts "hola de Rake!"
end



# Namespacing Rake Tasks
# NAMESPACE: A way to group or contain something, in this case our Rake tasks
namespace :greeting do
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end


# COMMON RAKE TASKS
# 1
# rake db:migrate
namespace :db do
  # Task Dependency - task needs to run the environment task before it can run migrate
  desc "migrate changes to the database"
  task migrate: :environment do
    Student.create_table
  end

  # creating an environment task
  desc "create the environment task"
  task :environment do
    require_relative "./config/environment"
  end

  # 2
  # rake db:seed - Responsible for "seeding" our database with some placeholder data.
  desc "seed the database with test data"
  task seed: :environment do
    require_relative "./db/seeds"
  end
end


# 3
# rake console - Helps interact with our class and database without having to run our entire program...
desc "Drop into the Pry console"
task console: :environment do
  Pry.start
end