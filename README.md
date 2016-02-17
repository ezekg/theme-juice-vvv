# Theme Juice VM

## Getting Started

### What is Vagrant?
[Vagrant](http://www.vagrantup.com) is a "tool for building and distributing development
environments". It works with [virtualization](http://en.wikipedia.org/wiki/X86_virtualization)
software such as [VirtualBox](https://www.virtualbox.org/) to provide a virtual machine
that is sandboxed away from your local environment.

### What do you get?
| Name                                                             | Version   | Description                                                                                                                                                                                                            |
| :--------------------------------------------------------------- | :-------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Ubuntu](http://www.ubuntu.com/)                                 | `14.04.3` | Ubuntu is a Debian-based Linux operating system and distribution for personal computers, smartphones and network servers.                                                                                              |
| [Apache](http://httpd.apache.org/)                               | `2.4.x`   | The Apache HTTP Server, colloquially called Apache, is the world's most used web server software.                                                                                                                      |
| [PHP](http://php.net/)                                           | `5.5.x`   | PHP (recursive acronym for PHP: Hypertext Preprocessor) is a widely-used open source general-purpose scripting language that is especially suited for web development and can be embedded into HTML.                   |
| [PHPBrew](https://github.com/phpbrew/phpbrew)                    | `stable`  | PHPBrew allows you to easily switch PHP versions.                                                                                                                                                                      |
| [MySQL](http://www.mysql.com/)                                   | `5.5.x`   | MySQL is an open-source relational database management system.                                                                                                                                                         |
| [WP-CLI](http://wp-cli.org/)                                     | `stable`  | WP-CLI is a set of command-line tools for managing WordPress installations.                                                                                                                                            |
| [Composer](https://getcomposer.org/)                             | `stable`  | Composer is a dependency manager for PHP.                                                                                                                                                                              |
| [Xdebug](http://xdebug.org/)                                     | `2.2.x`   | Xdebug is a PHP extension which provides debugging and profiling capabilities.                                                                                                                                         |
| [Webgrind](https://github.com/jokkedk/webgrind)                  | `stable`  | Webgrind is an Xdebug profiling web frontend in PHP.                                                                                                                                                                   |
| [Memcached](http://memcached.org/)                               | `1.4.x`   | Memcached (pronunciation: mem-cash-dee) is a general-purpose distributed memory caching system.                                                                                                                        |
| [phpMemcachedAdmin](https://code.google.com/p/phpmemcacheadmin/) | `1.2.x`   | phpMemcachedAdmin is an administration panel for Memcached for monitoring and debugging purposes.                                                                                                                      |
| [phpMyAdmin](http://www.phpmyadmin.net/)                         | `4.0.x`   | phpMyAdmin is a tool written in PHP, intended to handle the administration of MySQL over the Web.                                                                                                                      |
| [ack](http://beyondgrep.com/)                                    | `2.14.x`  | ack is a tool like grep, optimized for programmers.                                                                                                                                                                    |
| [git](http://git-scm.com/)                                       | `1.8.x`   | Git is a widely used source code management system for software development. It is a distributed revision control system with an emphasis on speed, data integrity, and support for distributed, non-linear workflows. |
| [ngrep](http://ngrep.sourceforge.net/usage.html)                 | `1.45.x`  | ngrep (network grep) is a network packet analyzer.                                                                                                                                                                     |
| [dos2unix](http://dos2unix.sourceforge.net/)                     | `6.0.x`   | dos2unix converts text files with DOS or Mac line endings to Unix line endings and vice versa.                                                                                                                         |
| [Node.js](https://nodejs.org/)                                   | `stable`  | Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient.                                                  |
| [npm](https://www.npmjs.com/)                                    | `stable`  | npm is a dependency manager for Node.js.                                                                                                                                                                               |
| [Grunt](http://gruntjs.com/)                                     | `stable`  | Grunt is a task runner for JavaScript.                                                                                                                                                                                 |

### Switching PHP versions
Create a new file called `provision/provision-post.sh` and add the PHP version
you would like to use, making sure it contains all 3 parts (i.e. `x.x.x`). See
the following example:

```bash
#!/bin/bash
php-switch 5.6.18 -y # -y skips all prompts
```

After that, provision the VM with `vagrant provision`. Bam! That easy!

Alternatively, you can `vagrant ssh` into the VM and run, for example,
```bash
php-switch 5.6.18
```

Using `php-switch` over SSH doesn't require you to provision the VM, so in the
end it is a lot faster. If you'd like to permanently use a specific PHP version,
you should use the `provision-post.sh` method, as that will persist even if
the VM is destroyed and re-created.

_Currently, this feature is limited to **only** PHP `5.x`. I haven't been able
to find a way to consistently configure other versions with Apache/MySQL. If
you have the chops, I'd love the help._

### Credentials and Such
| Program | User   | Pass   |
| :------ | :----- | :----- |
| MySQL   | `root` | `root` |

### Need Help?
* Let us have it! Don't hesitate to open a new issue on GitHub if you run into
  trouble or have any tips that we need to know.
