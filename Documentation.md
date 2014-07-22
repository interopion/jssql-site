---
title: Documentation
header: Documentation
group: navigation
layout: page
---

{% include JB/setup %}


<h3>JSSQLL Statement Syntax</h3>

<p class="titles">JSSQL <span class="orange">CREATE DATABASE</span> Syntax</p>

	CREATE DATABASE dbname;

<p class="titles">JSSQL CREATE TABLE</span> Syntax</p>

	CREATE TABLE table_name
	(
	column_name1 data_type(size),
	column_name2 data_type(size),
	column_name3 data_type(size),
	....
	);

<p class="titles">The <span class="orange">DROP TABLE</span> Statement</p>

<p>The DROP TABLE statement is used to delete a table.</p>

	DROP TABLE table_name

<p class="titles">The <span class="orange">DROP DATABASE</span> Statement</p>

<p>The DROP DATABASE statement is used to delete a database.</p>

	DROP DATABASE database_name

<p class="titles">JSSQL <span class="orange">INSERT INTO</span> Syntax</p>

	INSERT INTO table_name (column1,column2,column3,...)

	VALUES (value1,value2,value3,...);

<p class="titles">JSSQL <span class="orange">SELECT</span> Syntax</p>

	SELECT column_name,column_name
	FROM table_name;

<p>and</p>

	SELECT * FROM table_name;


<p class="titles">JSSQL <span class="orange">WHERE</span> Syntax</p>

	SELECT column_name,column_name
	FROM table_name
	WHERE column_name operator value;

<p class="titles">JSSQL <span class="orange">ORDER BY</span> Syntax</p>

	SELECT column_name,column_name
	FROM table_name
	ORDER BY column_name,column_name ASC|DESC;

<p class="titles">JSSQL <span class="orange">UPDATE</span> Syntax</p>

	UPDATE table_name
	SET column1=value1,column2=value2,...
	WHERE some_column=some_value;

<p class="titles">JSSQL <span class="orange">DELETE</span> Syntax</p>

	DELETE FROM table_name
	WHERE some_column=some_value;

<p class="titles">JSSQL <span class="orange">LIKE</span> Syntax</p>

	SELECT column_name(s)
	FROM table_name
	WHERE column_name LIKE pattern;

<p class="titles">JSSQL <span class="orange">IN</span> Syntax</p>

	SELECT column_name(s)
	FROM table_name
	WHERE column_name IN (value1,value2,...);


<p class="titles">JSSQL <span class="orange">BETWEEN</span> Syntax</p>

	SELECT column_name(s)
	FROM table_name
	WHERE column_name BETWEEN value1 AND value2;


<p class="titles">JSSQL <span class="orange">INNER JOIN</span> Syntax</p>

	SELECT column_name(s)
	FROM table1
	INNER JOIN table2
	ON table1.column_name=table2.column_name;

<p>or:</p>

	SELECT column_name(s)
	FROM table1
	JOIN table2
	ON table1.column_name=table2.column_name;

<p class="titles">JSSQL <span class="orange">LEFT JOIN</span> Syntax</p>

	SELECT column_name(s)
	FROM table1
	LEFT JOIN table2
	ON table1.column_name=table2.column_name;

<p>or:</p>

	SELECT column_name(s)
	FROM table1
	LEFT OUTER JOIN table2
	ON table1.column_name=table2.column_name;


<p class="titles">JSSQL <span class="orange">RIGHT JOIN</span> Syntax</p>

	SELECT column_name(s)
	FROM table1
	RIGHT JOIN table2
	ON table1.column_name=table2.column_name;

<p>or:</p>

	SELECT column_name(s)
	FROM table1
	RIGHT OUTER JOIN table2
	ON table1.column_name=table2.column_name;


<p class="titles">JSSQL <span class="orange">FULL OUTER JOIN</span> Syntax</p>

	SELECT column_name(s)
	FROM table1
	FULL OUTER JOIN table2
	ON table1.column_name=table2.column_name;

<p class="titles">JSSQL <span class="orange">SHOW</span> Syntax</p>

	SHOW tables from database_name;

<p class="titles">JSSQL <span class="orange">USE</span> Syntax</p>

	USE database_name;


<h3>Data types</h3>

<table class="reference notranslate">
<tr>
<th style="width:25%">Data type</th>
<th>Description</th>
</tr>
<tr>
<td>CHAR(n)</td>
<td>Character string. Fixed-length n</td>
</tr>
<tr>
<td>VARCHAR(n) or<br>CHARACTER VARYING(n)</td>
<td>Character string. Variable length. Maximum length n</td>
</tr>
<tr>
<td>BINARY(n)</td>
<td>Binary string. Fixed-length n</td>
</tr>
<tr>
<td>BIT</td>
<td>Stores TRUE or FALSE values</td>
</tr>
<tr>
<td>VARBINARY(n) or<br>BINARY VARYING(n)</td>
<td>Binary string. Variable length. Maximum length n</td>
</tr>
<tr>
<td>INTEGER(p)</td>
<td>Integer numerical (no decimal). Precision p</td>
</tr>
<tr>
<td>TINYINT</td>
<td>Holds a string with a maximum length of 255 characters</td>
</tr>
<tr>
<td>MEDIUMINT</td>
<td>-8388608 to 8388607 normal. 0 to 16777215 UNSIGNED*. The maximum number of digits may be specified in parenthesis</td>
</tr>
<tr>
<td>SMALLINT</td>
<td>Integer numerical (no decimal). Precision 5</td>
</tr>
<tr>
<td>DOUBLE</td>
<td>A large number with a floating decimal point. The maximum number of digits may be specified in the size parameter. The maximum number of digits to the right of the decimal point is specified in the d parameter</td>
</tr>
<tr>
<td>INTEGER</td>
<td>Integer numerical (no decimal). Precision 10</td>
</tr>
<tr>
<td>BIGINT</td>
<td>Integer numerical (no decimal). Precision 19</td>
</tr>
<tr>
<td>DECIMAL(p,s)</td>
<td>Exact numerical, precision p, scale s. Example: decimal(5,2) is a 
number that has 3 digits before the decimal and 2 digits after the decimal</td>
</tr>
<tr>
<td>NUMERIC(p,s)</td>
<td>Exact numerical, precision p, scale s. (Same as DECIMAL)</td>
</tr>
<tr>
<td>FLOAT(p)</td>
<td>Approximate numerical, mantissa precision p. A floating number in base 
10 exponential notation. The size argument for this type consists of a 
single number specifying the minimum precision</td>
</tr>
<tr>
<td>BLOB</td>
<td>For BLOBs (Binary Large OBjects). Holds up to 65,535 bytes of data</td>
</tr>
<tr>
<td>MEDIUMBLOB</td>
<td>For BLOBs (Binary Large OBjects). Holds up to 16,777,215 bytes of data</td>
</tr>
<tr>
<td>LONGBLOB </td>
<td>For BLOBs (Binary Large OBjects). Holds up to 4,294,967,295 bytes of data</td>
</tr>
<tr>
<td>TINYBLOB </td>
<td>Binary data with variable length, maximum 255 bytes</td>
</tr>
<tr>
<td>TINYTEXT</td>
<td>Holds a string with a maximum length of 255 characters</td>
</tr>
<tr>
<td>TEXT</td>
<td>Holds a string with a maximum length of 65,535 characters</td>
</tr>
<tr>
<td>MEDIUMTEXT</td>
<td>Holds a string with a maximum length of 16,777,215 characters</td>
</tr>
<tr>
<td>LONGTEXT</td>
<td>Holds a string with a maximum length of 4,294,967,295 characters</td>
</tr>
<tr>
<td>ENUM(x,y,z,etc.)</td>
<td>Let you enter a list of possible values. You can list up to 65535 values in an ENUM list. If a value is inserted that is not in the list, a blank value will be inserted.
Note: The values are sorted in the order you enter them.
You enter the possible values in this format: ENUM('X','Y','Z')	</td>
</tr>
<tr>
<td>REAL</td>
<td>Approximate numerical, mantissa precision 7</td>
</tr>
<tr>
<td>FLOAT</td>
<td>Approximate numerical, mantissa precision 16</td>
</tr>
<tr>
<td>DATE</td>
<td>Stores year, month, and day values</td>
</tr>
<tr>
<td>TIME</td>
<td>Stores hour, minute, and second values</td>
</tr>
<tr>
<td>DATETIME</td>
<td>A date and time combination. Format: YYYY-MM-DD HH:MM:SS</td>
</tr>
<tr>
<td>TIMESTAMP</td>
<td>Stores year, month, day, hour, minute, and second values</td>
</tr>
<tr>
<td>YEAR</td>
<td>A year in two-digit or four-digit format.</td>
</tr>
<tr>
<td>SET</td>
<td>A variable-length and unordered collection of elements</td>
</tr>
</table>



<h3>Reserved words</h3>

Certain words such as SELECT, DELETE, or BIGINT are reserved and require special treatment for use as identifiers such as 
table and column names.


<div>
<table class="reserved_words" border="1">
<tr>
<td>
<p>
<span>
<span class="input">ABSOLUTE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">EXEC</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">OVERLAPS</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ACTION</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">EXECUTE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PAD</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ADA</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">EXISTS</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PARTIAL</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ADD</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">EXTERNAL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PASCAL</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ALL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">EXTRACT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">POSITION</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ALLOCATE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FALSE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PRECISION</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ALTER</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FETCH</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PREPARE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">AND</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FIRST</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PRESERVE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ANY</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FLOAT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PRIMARY</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ARE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FOR</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PRIOR</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">AS</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FOREIGN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PRIVILEGES</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ASC</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FORTRAN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PROCEDURE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ASSERTION</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FOUND</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">PUBLIC</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">AT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FROM</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">READ</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">AUTHORIZATION</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">FULL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">REAL</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">AVG</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">GET</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">REFERENCES</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">BEGIN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">GLOBAL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">RELATIVE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">BETWEEN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">GO</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">RESTRICT</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">BIT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">GOTO</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">REVOKE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">BIT_LENGTH</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">GRANT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">RIGHT</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">BOTH</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">GROUP</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">ROLLBACK</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">BY</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">HAVING</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">ROWS</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CASCADE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">HOUR</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SCHEMA</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CASCADED</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">IDENTITY</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SCROLL</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CASE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">IMMEDIATE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SECOND</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CAST</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">IN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SECTION</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CATALOG</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INCLUDE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SELECT</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CHAR</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INDEX</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SESSION</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CHAR_LENGTH</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INDICATOR</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SESSION_USER</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CHARACTER</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INITIALLY</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SET</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CHARACTER_LENGTH</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INNER</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SIZE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CHECK</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INPUT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SMALLINT</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CLOSE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INSENSITIVE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SOME</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">COALESCE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INSERT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SPACE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">COLLATE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SQL</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">COLLATION</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INTEGER</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SQLCA</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">COLUMN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INTERSECT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SQLCODE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">COMMIT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INTERVAL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SQLERROR</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CONNECT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">INTO</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SQLSTATE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CONNECTION</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">IS</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SQLWARNING</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CONSTRAINT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">ISOLATION</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SUBSTRING</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CONSTRAINTS</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">JOIN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SUM</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CONTINUE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">KEY</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">SYSTEM_USER</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CONVERT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">LANGUAGE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TABLE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CORRESPONDING</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">LAST</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TEMPORARY</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">COUNT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">LEADING</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">THEN</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CREATE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">LEFT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TIME</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CROSS</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">LEVEL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TIMESTAMP</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CURRENT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">LIKE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TIMEZONE_HOUR</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CURRENT_DATE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">LOCAL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TIMEZONE_MINUTE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CURRENT_TIME</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">LOWER</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TO</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CURRENT_TIMESTAMP</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">MATCH</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TRAILING</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CURRENT_USER</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">MAX</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TRANSACTION</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">CURSOR</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">MIN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TRANSLATE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DATE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">MINUTE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TRANSLATION</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DAY</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">MODULE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TRIM</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DEALLOCATE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">MONTH</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">TRUE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DEC</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NAMES</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">UNION</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DECIMAL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NATIONAL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">UNIQUE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DECLARE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NATURAL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">UNKNOWN</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DEFAULT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NCHAR</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">UPDATE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DEFERRABLE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NEXT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">UPPER</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DEFERRED</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NO</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">USAGE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DELETE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NONE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">USER</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DESC</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NOT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">USING</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DESCRIBE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NULL</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">VALUE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DESCRIPTOR</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NULLIF</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">VALUES</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DIAGNOSTICS</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">NUMERIC</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">VARCHAR</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DISCONNECT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">OCTET_LENGTH</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">VARYING</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DISTINCT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">OF</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">VIEW</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DOMAIN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">ON</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">WHEN</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DOUBLE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">ONLY</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">WHENEVER</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">DROP</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">OPEN</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">WHERE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ELSE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">OPTION</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">WITH</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">END</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">OR</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">WORK</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">END-EXEC</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">ORDER</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">WRITE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">ESCAPE</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">OUTER</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">YEAR</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">EXCEPT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">OUTPUT</span>
</span>
</p>
</td>
<td>
<p>
<span>
<span class="input">ZONE</span>
</span>
</p>
</td>
</tr>
<tr>
<td>
<p>
<span>
<span class="input">EXCEPTION</span>
</span>
</p>
</td>
<td>
<p> </p>
</td>
<td>
<p> </p>
</td>
</tr>
</table>
</div>



