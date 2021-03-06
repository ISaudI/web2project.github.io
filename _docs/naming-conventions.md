---
layout: page
title: Naming Conventions

category: "module building guide"
status: cleanup
---

Web2project works on the basis of *"The easy way should also be the right way."* A key reason that this works is because of our Naming Conventions. It allows quite a few things to "just work" without additional effort, configuration, or coding by anyone working on any module. As long as you stick to our conventions, your modules and customizations should need minimal updates between web2project releases.

There are three layers of the system that all interact together: the database, the module's business logic, and the view/templating layer. Since everything begins with the module, we'll begin there.

## Modules

* Modules MUST have a unique name;
* The module directory MUST be lower case alphanumeric with no special characters - ex: projects, links;
* The module's files MUST be contained within its directory within the */modules/* directory exclusively;
* The module MUST have a file named setup.php with a setup class that extends w2p_Core_Setup;
* The module's subclass file MUST be the plural form of the subclass name followed by '.class.php' - ex: File Folder -> files/folders.class.php, Task Logs -> tasks/logs.class.php;
* The module directory SHOULD be the plural form of the module name - ex: Project -> projects, Companies -> companies;
* The module class file SHOULD be the plural form of the module name followed by '.class.php - ex: Project -> projects.class.php, Companies -> companies.class.php;
* The module MAY have subclasses;
* The module MAY have a file named configure.php which allows for module-specific settings.

## Database

* The data table - different from linking or many:many tables - SHOULD be the plural form of the module name: ex: Project -> projects, Task -> tasks;
* Fields of the data tables SHOULD be prefixed with the singular form of the module name - ex: project_id, project_name;
* Foreign key relationships to other modules SHOULD be named modulename_othermodulename - ex: project_company links a Project to a specific Company, task_project links a Task to a specific Project;
* Fields which are enumerated types SHOULD be stored as integers referring to specific System Lookup Values;
* Fields which are enumerated types MUST have names which are easily converted to their System Lookup Values - ex: company_type -> CompanyType, project_status -> ProjectStatus, task_priority -> TaskPriority;
* Field names SHOULD be expressive towards what they are: ex: project_id is the primary key, project_name is the name of the project;
* Data types SHOULD be reflected via column name suffixes as described here: 

Suffix  | Example | Description
----- | ----- | -----
_id | project_id, company_id | This is the primary key of the database table.
_budget | project_actual_budget | This is a simple text field displayed with the user's preferred currency symbol. For rendering, it will always appear in the users' preferred currency format.
_date | project_start_date, project_end_date | This is a simple text field displayed with a date picker for editing purposes. For rendering, it will always appear in the users' preferred short date format. It is not timezone sensitive aware and should not have user or system timezones applied.
_datetime | (not used in the core system) | This is a simple text field displayed with both a date and time picker for editing purposes. It is timezone aware and is stored in the database in UTC. For rendering, it will always appear in the users' preferred long date format transformed according to their specified timezone.
_description | company_description, project_description | This is always a dataype of 'text' and displayed in a textarea for editing purposes. For rendering, it automatically keeps all linebreaks and makes any urls clickable.
_email | company_email, contact_email | This is a simple text field. For rendering, it is automatically made clickable with a mailto link.
(module names) | project_company, task_project, link_project | This is the most complex datatype currently in the system. It is usually displayed as a dropdown for editing purposes but may be handled via other means. For rendering purposes, it uses the specific suffix - company, project, department, task, user, etc - to lookup that object's name and link to it directly.
_name | company_name, project_name, task_name | This is a simple text field. For rendering, it is made clickable to view the named object.
_percent | (none currently in the system) | This is usually calculated automatically by the system. Where it is editable, it will be a dropdown populated by integers ranging from 0 to 100. For rendering, a percent sign is added.
_url | task_related_url, project_url | This is a simple text field with a 'test' link button for editing purposes. For rendering, it is automatically made clickable.

## Module Class(es)

* The class name SHOULD be the singular form of the module name prefixed by the letter C - ex: Departments -> CDepartment, Contacts -> CContact;
* The class's public properties MUST be named identically to its database table's columns - ex: CProject->project_id -> projects/project_id, CForum->forum_name -> forums/forum_name;
* The class MAY have protected properties;
* The class SHOULD NOT have any private properties;
* The class's primary id property should end with '_id' - ex: CProject->project_id, CCompany->company_id;
* The class's name property should end with '_name' - ex: CTask->task_name, CEvent->event_name;
* A module MAY have subclasses;
* Subclass(es) name MUST be the singular form of the module name prefixed by the letter C and then followed by an underscore (_) and singular form of the subclass - ex: File Folders -> CFile_Folder, Task Logs -> CTask_Log;
* All classes and subclasses MUST respect core web2project permissions and ACLs;

## View/Templating

* The module MUST have a file named index.php which usually generates a list table of items;
* The module SHOULD have a file named addedit.php which includes the HTML form to create or edit an item;
* The module MAY have a file named view.php which displays all of the information related to an item;
* The list table and view.php files SHOULD use the w2p_Output_HTMLHelper to format each data field properly.

## Exceptions

Unfortunately, there are some oddball legacy modules/classes that break the above conventions. We're stuck with for the time being but intend to correct them over time

* <s>The main class for the Calendar Module is actually **CEvent** and in *modules/calendar/calendar.class.php* instead of being **CCalendar** in *modules/calendars/calendars.class.php* as you'd expect;</s> - Resolved in v3.1 by renaming the Calendar module to Events.
* <s>The main class for the User Admin Module is actually **CUser** and in the *modules/admin/users.class.php* instead of being **CAdmin** in *modules/admins/admins.class.php* as you'd expect;</s> - Resolved in v3.1 by renaming the Admin module to Users.
* The directories and main classes for the System Admin, SmartSearch, Project Designer, and History Modules are in folders and files with singular nouns instead of plural as you'd expect;
  * There's no specific plan of action to correct these oddities;
* The Department Module's database structure correctly names the table 'departments' but uses the column name prefix of 'dept' instead of the expected 'department'.

These oddities along with a few others make our [class autoloader](https://github.com/web2project/web2project/blob/master/includes/main_functions.php#L18) a huge pain. Further, the formatting helper ([w2p_Output_HTMLHelper](https://github.com/web2project/web2project/blob/master/classes/w2p/Output/HTMLHelper.class.php)) has so many oddball exceptions that it drives me up the wall.