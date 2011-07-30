Setup
====

gem install bundle
bundle install

JAVA SDK
====

/System/Library/Frameworks/JavaVM.framework/Versions/Current/JavaVM

Mysql
====

$ brew install mysql
$ sudo vi ~/.my.cnf

	[mysqld]
	datadir=/usr/local/var/mysql/mysql
	socket=/usr/local/var/mysql/mysql.sock
	character-set-server=utf8
	max_allowed_packet=8M

	#This option makes InnoDB to store each created table into its own .ibd file.
	innodb_file_per_table

	[mysql]
	default-character-set=utf8

	[client]
	socket=/usr/local/var/mysql/mysql.sock

$ unset TMPDIR
$ mysql_install_db --verbose --user=$USER --basedir="$(brew --prefix mysql)" --tmpdir=/tmp
$ mysql_secure_installation
$ mysql.server start
$ mysql.server stop

buildr
====

buildr -t
buildr mvcdemo:web:jetty
buildr mvcdemo:web:run

buildr idea:generate
buildr idea:clean

Notes
====

[BUG] cross-thread violation on rb_gc()
(null)

How to fix:

  $ gem uninstall rjb 
  Select gem to uninstall:
   1. rjb-1.3.3
   2. rjb-1.3.3-universal-darwin-10
   3. All versions
  > 2
