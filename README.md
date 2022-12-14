
# Steps taken to create this app
This readme is very rough currently and will be improved as development of this
app continues.

---
# DAY ONE

## rails
```
% rails -v
Rails 6.1.4.4
```

install latest rails 7
`% gem install rails`

confirm latest rails version
```
% rails -v
Rails 7.0.4
```

## ruby
Confirm current version of ruby
```
% ruby --version
ruby 2.7.4p191 (2021-07-07 revision a21a3b7d23) [x86_64-darwin20]
```

## postgres
```
% psql -V
psql (PostgreSQL) 14.5 (Homebrew)

% gem install pg

% pg_ctl -D /usr/local/var/postgres start
```

If you run into this error:
```
FATAL:  database files are incompatible with server
2022-10-01 19:20:10.912 EST [42278] DETAIL:  The data directory was initialized by PostgreSQL version 13, which is not compatible with this version 14.5 (Homebrew).
```

Use this to upgrate your database from 13 to 14:
```
% brew postgresql-upgrade-database
```

This command should now work:
```
% pg_ctl -D /usr/local/var/postgres start
waiting for server to start....2022-10-01 19:25:19.684 EST [42870] LOG:  starting PostgreSQL 14.5 (Homebrew) on x86_64-apple-darwin20.6.0, compiled by Apple clang version 13.0.0 (clang-1300.0.29.30), 64-bit
2022-10-01 19:25:19.686 EST [42870] LOG:  listening on IPv6 address "::1", port 5432
2022-10-01 19:25:19.686 EST [42870] LOG:  listening on IPv4 address "127.0.0.1", port 5432
2022-10-01 19:25:19.687 EST [42870] LOG:  listening on Unix socket "/tmp/.s.PGSQL.5432"
2022-10-01 19:25:19.691 EST [42871] LOG:  database system was shut down at 2022-10-01 19:25:02 EST
2022-10-01 19:25:19.694 EST [42870] LOG:  database system is ready to accept connections
 done
server started
```

Additional useful psql commands.
```
% psql -l
                                    List of databases
   Name    |     Owner     | Encoding | Collate | Ctype |        Access privileges
-----------+---------------+----------+---------+-------+---------------------------------
 postgres  | susanprestage | UTF8     | C       | C     |
 template0 | susanprestage | UTF8     | C       | C     | =c/susanprestage               +
           |               |          |         |       | susanprestage=CTc/susanprestage
 template1 | susanprestage | UTF8     | C       | C     | susanprestage=CTc/susanprestage+
           |               |          |         |       | =c/susanprestage
(3 rows)

% psql -U postgres -h localhost
psql (14.5 (Homebrew))

% psql -U postgres -h localhost
psql (14.5 (Homebrew))
Type "help" for help.

postgres=# create role rails7testapp with createdb login password 'BseeingU2';
CREATE ROLE
```


% rails new rails7-test-app --database=postgresql

% rake db:setup

% rails webpacker:install
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
rails aborted!
Don't know how to build task 'webpacker:install' (See the list of available tasks with `rails --tasks`)

Need to install Nodejs
% node -v
v16.17.1

And Yarn
% npm install --global yarn

Transpile app-like JavaScript. Read more: https://github.com/rails/webpacker
gem 'webpacker', '~> 5.0'

% rails webpacker:install

Should be ready now to run the new rails app.
% rails s -p 3001

Create our first model
% rails g scaffold Post title:string body:text

Run the first migration to pick up the above changes
% rake db:migrate



---

Leaving this original readme here to review for ideas with the goal of ensuring
the readme for this app is complete and useful.  -sprestage

# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
