# laravel-backup
Creating for backup of database and files of project. <br />
composer install <br />
composer update <br />
rename .env.example to .env file <br />
define your database there <br />
php artisan migrate <br />
npm install <br />
npm run dev <br />
php artisan vendor:publish --provider="Spatie\Backup\BackupServiceProvider" <br />
<!-- Define below code in config/database.php  --> <br />
Note : Check your mysqldump file path and define in ‘'dump_binary_path' <br />
'connections' => [ <br />
	'mysql' => [ <br />
		'driver'    => 'mysql' <br />
		..., <br />
		'dump' => [ <br />
		   'dump_binary_path' => '/path/to/the/binary', // only the path, so without `mysqldump`  or `pg_dump` <br />
		   'use_single_transaction', <br />
		   'timeout' => 60 * 5, // 5 minute timeout <br />
		   // comment last 2 fields <br />
		   // 'exclude_tables' => ['table1', 'table2'], <br />
		   // 'add_extra_option' => '--optionname=optionvalue', <br />
		]  <br />
	], <br />

php artisan backup:run
