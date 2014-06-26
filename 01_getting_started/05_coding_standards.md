# Coding standards

--------------------------------------------------------

* [PHP tags](#php_tags)
* [Files](#files)
* [Namespaces](#namespaces)
* [Classes](#classes)
* [Methods](#methods")
* [Variables](#variables)
* [Constants](#constants)
* [Braces](#braces)
* [Indentation](#indentation)
* [Comments](#comments)

--------------------------------------------------------

The following coding standards have been used when developing Mako. We suggest you follow the same standards when developing applications using Mako.

--------------------------------------------------------

<a id="php_tags"></a>

### PHP tags

Always use long open tags. Never use short tags or ASP style tags. Class files should never include a closing tag.

	// Correct

	<?php

	// Incorrect

	<?

	// Incorect

	<%

--------------------------------------------------------

<a id="files"></a>

### Files

Files should always have the same name as the class they contain. A file should never contain more than one class. The file encoding should always be UTF-8.

File names must match the case of the class. The only exception being controllers and tasks, which should always have lower case file names.

	// File: libraries/mako/DateTime.php

	<?php

	namespace mako
	{
		class DateTime
		{
			
		}
	}

	// File: app/controllers/index.php

	<?php

	namespace app\lib
	{
		class Index
		{
			
		}
	}

--------------------------------------------------------

<a id="namespaces"></a>

### Namespaces

Namespaces should be written in lower case:

	// Correct

	namespace foo\bar;

	// Incorrect

	namespace Foo\Bar;

--------------------------------------------------------

<a id="classes"></a>

### Classes

Class names should be written in upper CamelCase:

	// Correct

	class Image

	// Correct

	class MyImage

	// Incorrect

	class image

	// Incorrect

	class my_image

--------------------------------------------------------

<a id="methods"></a>

### Methods

Method names should be written in lower camelCase (does not apply to controller and task methods):

	// Correct

	public function fooBar()

	// Incorrect

	public function FooBar()

	// Incorrect

	public function foo_bar()

--------------------------------------------------------

<a id="variables"></a>

### Variables

Variable names should be written in lower camelCase:

	// Correct

	$fooBar = null;

	// Incorrect

	$foobar = null;

	// Incorrect

	$foo_bar = null;

--------------------------------------------------------

<a id="constants"></a>

### Constants

Constant names should be written in upper case and multiple words should be separated with a underscore:

	// Correct

	const FOO_BAR = 123;

	// Correct

	define('FOO_BAR', 123);

	// Incorrect

	const foobar = 123;

	// Incorrect

	define('foobar', 123);

--------------------------------------------------------

<a id="braces"></a>

### Braces

Braces associated with a control statement should always be on the next line, indented to the same level as the control statement:

	// Correct

	public function foo()
	{
		
	}

	// Incorrect

	public function foo() {

	}

--------------------------------------------------------

<a id="indentation"></a>

### Indentation

Tabs should be used for indentation while spaces should be used to align code:

	<?php

	namespace foo;

	class Bar
	{
		public function hello()
		{
			$string  = 'Hello ';
			$string .= 'World!';

			echo $string;
		}
	}

--------------------------------------------------------

<a id="comments"></a>

### Comments

All classes, methods and functions are commented using the [PHPDoc](http://en.wikipedia.org/wiki/PHPDoc) standard.

This makes it easy to understand what the code does and it also enables IDEs to provide improved code completion, type hinting and debugging.

	/**
	 * Returns a greeting.
	 * 
	 * @access  public
	 * @param   string  $name  Name of the person you want to greet
	 * @return  string
	 */

	public function greeting($name)
	{
		return 'Hello, ' . $name . '!';
	}