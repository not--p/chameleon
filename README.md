# Chameleon Framework Documentation
[Live Documentation](http://chameleon.lakonacomputers.com)

## Table of Contents

* I. [Getting Started](#gettingStarted)
    * [Cloning](#cloning)
    * [Chameleon Setup](#setup)
* II. [Conventions](#conventions)

<h2 id=\"gettingStarted\">Getting Started</h2>
The Chameleon framework is used to quickly setup new WWW applications. It
currently only supports applications using Apache (2.6) webserver on Ubuntu.
Begin by cloning chameleon into a directory (making sure the desired ower and
group are set). Then run `sudo ./bin/chameleon setup`. This will require user
interaction to setup the WWW application project. It's helpful to know how to
setup Apache webserver.

### Cloning <span id=\"cloning\"></span>

    git clone https://github.com/not--p/Chameleon [project-dir]
    
### Running the Chameleon script <span id=\"setup\"></span>

    sudo ./bin/chameleon setup
    

## Conventions <span id=\"conventions\"></span>

### Directory Structure

**conf** → contains configuration templates.

**log** → contains the log files.

**resources** → contains `css`, database (`db`), `html`, image (`img`), javascript (`js`), and `php`.

**vendor** → contains composer components.

**views** → contains pages/scripts that are shown to the user.

#### Notes on Directory Structure

-- The chameleon (bin/chameleon) script 

### DIR Constants
All PHP constants defined in Chameleon that represent directories and
are named 'such-and-such' `DIR` (i.e. `CSS_DIR`, `JS_DIR`, etc) end
with a trailing slash.

## Chameleon Script

The chameleon script (located in the root directory of the application)
runs with root permissions.

The usage is as follows:

    setup:         run this command to initialize a chameleon project. 
    index:         restore/create the default index.php file. 
    css:           restore/create the default custom.css file. 
    config-php:    (re)configure project's PHP (config.php) 
    config-js:     (re)configure project's JavaScript (resources/js/config.js) 
    config-apache: (re)configure project's Apache configuration. 
    logs:          (re)create project's log directory and log files.

## config.js

The JavaScrip for Chameleon is configured in the **config.js** file.
The template for this file is found in the conf directory and the live
configuration file is located in **resources/js/config.js** with the
rest of the project's JavaScript files.

The configuration file defines the project's **APP** object (`{}`). The
APP object is global and can be extended. Simply add data and methods
to APP (e.g. `APP.name='chameleon'`).

### JavaScript APP Object

#### Data Members

    requestURL: Stores the url where requests are directed.
    
#### Functional Members


## Request Handling

By default requests are handled by `RequestHandler.php` located in the APP_ROOT.
RequestHandler is created from a template file in the `conf` directory. Simply
add methods to this class for each GET or POST request you want to handle.

