# magento2
Magento 2 with Sample Data

<h2>Installation instructions</h2>
<h2>Step 1: Verify your prerequisites</h2>

Use the following table to verify you have the correct prerequisites to install the Magento software.

<table>
	<tbody>
		<tr>
			<th>Prerequisite</th>
			<th>How to check</th>
			<th>For more information</th>
		</tr>
	<tr>
		<td>Apache 2.2 or 2.4</td>
		<td>Ubuntu: <code>apache2 -v</code><br>
		CentOS: <code>httpd -v</code></td>
		<td><a href="http://devdocs.magento.com/guides/v2.0/install-gde/prereq/apache.html">Apache</a></td>
	</tr>
	<tr>
		<td>PHP 5.5.x or 5.6.x</td>
		<td><code>php -v</code></td>
		<td><a href="http://devdocs.magento.com/guides/v2.0/install-gde/prereq/php-ubuntu.html">PHP Ubuntu</a><br><a href="http://devdocs.magento.com/guides/v2.0/install-gde/prereq/php-centos.html">PHP CentOS</a></td>
	</tr>
	<tr><td>MySQL 5.6.x</td>
	<td><code>mysql -u [root user name] -p</code></td>
	<td><a href="http://devdocs.magento.com/guides/v2.0/install-gde/prereq/mysql.html">MySQL</a></td>
	</tr>
</tbody>
</table>


<h2>Step 2: GIT Clone</h2>
<code>
  git clone https://github.com/emizentech/magento2.git
</code>

<h2>Step 3: Create and Import Database</h2>
<pre>
  *# untar mageto2.sql.tar.gz file
  tar -xzf mageto2.sql.tar.gz
  *# now create database using terminal or phpMyAdmin and import mageto2.sql file
  *# change URL in core_config_data table chage URL  for key web/unsecure/base_url &  web/secure/base_url
</pre>

<h2>Step 4: Set DB Credentials</h2>
<ul>
<li>
  remame app/etc/env.php.sample to app/etc/env.php and set database credentials
  <pre>
    'db' => 
  array (
    'table_prefix' => '',
    'connection' => 
    array (
      'default' => 
      array (
        'host' => 'localhost', // Change if you have any other host for mysql
        'dbname' => 'magento2', // change your db name here
        'username' => 'username', // change your username here
        'password' => 'password', // change your password here
        'active' => '1',
      ),
    ),
  </pre>
  if you want to change admin path 
  than change here 
  <pre>
      'backend' => 
        array (
          'frontName' => 'admin',
        ),
  </pre>
  
</li>
</ul>

<h2>Step 4: Set Permission and run website</h2>
<pre>
  chown -R admin:www-data /var/www/magento2
  find /var/www/magento2 -type f -print0 | xargs -r0 chmod 640
  find /var/www/magento2 -type d -print0 | xargs -r0 chmod 750
  chmod -R g+w /var/www/magento2/{pub,var}
</pre>

<h3>default admin credentials </h3>

<pre>
username : admin 
password : admin@123!
</pre>
