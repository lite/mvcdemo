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

buildr -T
buildr mvcdemo:web:jetty
