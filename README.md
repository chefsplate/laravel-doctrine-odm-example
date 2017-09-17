# laravel-doctrine-odm-example [WIP]

Example [Laravel](https://github.com/laravel/laravel) project demonstrating usage of the 
[Laravel-Doctrine-ODM wrapper](https://github.com/chefsplate/laravel-doctrine-odm) 
for creating an API for a todo list service, similar to [Todoist](https://todoist.com)! 

Entities can be found under app/Entities, and API endpoints can be found in app/Http/Controllers.

# Requirements

- PHP mongo extension (ext-mongo) must be installed: http://php.net/manual/en/mongo.installation.php
    - On a Mac, the easiest way to install this extension is through `brew`: `brew install php56` followed by `brew install php56-mongo`

## Install

Install this example by typing

    composer install

at the root of the project.

Configure the Mongo connection within config/database.php to point to your Mongo instance:

    'mongodb' => array(
        'driver'   => 'mongodb',
        'dsn'      => 'mongodb://127.0.0.1:27017',
        'database' => 'todos'
    ),

More installation details are available on the [Laravel-Doctrine-ODM wrapper](https://github.com/chefsplate/laravel-doctrine-odm) 
project page if you are setting this up on your existing projects.

# Data model

- Users have projects (we will create an inbox)
- Projects have tasks
- Tasks have description, notes, labels, due date and status

# API

In this example, we will implement the following operations:

Request Type | Operation
--- | ---
GET | Users can fetch their projects and tasks
POST | Users can create tasks within a project (e.g. Inbox)
PUT | Users can mark a task as complete
DELETE | Users can delete a task
GET | Users can get a list of all incomplete tasks due in next 7 days (Today view)

Note: This example is a work-in-progress.