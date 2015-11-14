---
layout: default
---

<s>Release Date: 09 December 2009</s>

'''v1.2.2 Patch Release Date:''' 06 January 2010

'''''NOTICE:'''  This is no longer the latest version available.  Please check the sidebar at left for the latest release notes.''

== Downloading web2project ==

For the v1.2.2 Release, the only official distribution site is [https://sourceforge.net/projects/web2project/files/web2Project/v1.2.x%20Release/ SourceForge].

All Installation instructions  have been moved to the [[Installation]] page. They will no longer be included in the Release Notes.

== Reporting Problems ==

Any and all issues discovered should be added to our [http://bugs.web2project.net/view_all_bug_page.php our Issue Tracking System].  Feature requests should be marked as such and not described as bugs.

For more information, support, or to discussion upcoming features, please visit [http://forums.web2project.net/ our Support Forums].

== New Features ==

=== v1.2.1 / 1.2.2 ===

*  Updated two file permissions issues to allow compatibility with IIS7+

=== v1.2 ===

*  Added description and url information to iCal entries to make them more useful
*  Added object validation to all core modules to ensure that all required fields are set (relates to 242 below), further when an object fails validation, the user's input is sent back to the proper addedit page, their input is not lost
*  Standardized the method signatures for all core modules to simplify API development
*  Changed the Total Hours, Task Count, Percent Complete, and Worked Hours calculations to happen during selected updates and simply cache them for later requests
*  Added function files to track and notify users of functions that exist for backwards compatibility (mostly with PHP itself) and functions which will be deprecated
*  [http://bugs.web2project.net/view.php?id=170 170] - Projects - Cache Worked/Scheduled/Project Hours (caseydk)
*  [http://bugs.web2project.net/view.php?id=190 190] - Core Infrastructure - Build an Autoloader (caseydk)
*  [http://bugs.web2project.net/view.php?id=242 242] - Core Infrastructure - Display of server side validation (caseydk)
*  [http://bugs.web2project.net/view.php?id=274 274] - Roles: Import Permissions from existing Roles when creating new ones (pedroa)

== Fixes/Bugs Closed ==

=== v1.2.1/.2 ===

There were a total of seven particularly annoying and/or troublesome issues that made it into the v1.2 release  and have been fixed in the v1.2.1 release (pending).  While this frustrating for many, we appreciate the great community that has proven excellent in finding, diagnosing, and confirming bugs.  This effort wouldn't work without them.

*  [http://bugs.web2project.net/view.php?id=329 329] - Trying to add a new department is not possible. Department Company field not populated.
*  [http://bugs.web2project.net/view.php?id=330 330] - Can't add/edit contacts
*  [http://bugs.web2project.net/view.php?id=331 331] - Contact edit form is blank
*  [http://bugs.web2project.net/view.php?id=333 333] - Can't see documents under documents TAB
*  [http://bugs.web2project.net/view.php?id=335 335] - Version 1.2 bug: can not delete files
*  [http://bugs.web2project.net/view.php?id=350 350] - Installation issue
*  [http://bugs.web2project.net/view.php?id=351 351] - Create User

=== v1.2 ===

*  Fixed some issues with the iCal interface
*  Updated the Contacts search to work properly
*  [http://bugs.web2project.net/view.php?id=143 143] - Projects - Project % Complete Calculations (caseydk)
*  [http://bugs.web2project.net/view.php?id=152 152] - Tasks - Task not displayed in Todo (pedroa)
*  [http://bugs.web2project.net/view.php?id=168 168] - Calendar - problems with tabs in todo when adding additional module (caseydk)
*  [http://bugs.web2project.net/view.php?id=245 245] - UTF8 handling errors (pedroa)
*  [http://bugs.web2project.net/view.php?id=253 253] - Core Infrastructure - Can't logon w2p !!! (trevormorse)
*  [http://bugs.web2project.net/view.php?id=254 254] - Tasks - Unauthorized view of compenies and users when assigning people to a task (pedroa)
*  [http://bugs.web2project.net/view.php?id=255 255] - Contacts - Issues on the Contacts Search (caseydk)
*  [http://bugs.web2project.net/view.php?id=256 256] - Core Infrastructure - Multiple email sent (pedroa)
*  [http://bugs.web2project.net/view.php?id=261 261] - Reports - "Tasks sorted by user" has dates only in European format (caseydk)
*  [http://bugs.web2project.net/view.php?id=262 262] - Tasks - Ckick on "todo" button doesn't refresh task list (pedroa)
*  [http://bugs.web2project.net/view.php?id=263 263] - Tasks - Task I have created not returned correctly (pedroa)
*  [http://bugs.web2project.net/view.php?id=266 266] - Forums - Fatal error when accessing a forum (pedroa)
*  [http://bugs.web2project.net/view.php?id=267 267] - Core Infrastructure - Not send email when using the option: Help! I've forgotten my password! (pedroa)
*  [http://bugs.web2project.net/view.php?id=268 268] - Files - Softcode strings to ignore in file indexation (caseydk)
*  [http://bugs.web2project.net/view.php?id=269 269] - potential corruption of UTF-8 character strings (pedroa)
*  [http://bugs.web2project.net/view.php?id=273 273] - Wrong Day spell in jscalendar (pedroa)
*  [http://bugs.web2project.net/view.php?id=278 278] - Departments - insert or update Department uses bad dept_parent value (caseydk)
*  [http://bugs.web2project.net/view.php?id=284 284] - Files - The W2P is allowing delete files linked to a project that the user not participating in the project. (caseydk)
*  [http://bugs.web2project.net/view.php?id=286 286] - Core Infrastructure - New autoload doesn't support loading Mail (caseydk)
*  [http://bugs.web2project.net/view.php?id=291 291] - Permissions - SQL error in editing permission (caseydk)
*  [http://bugs.web2project.net/view.php?id=294 294] - Project Designer - Project hours different/not accurate in project designer (caseydk)
*  [http://bugs.web2project.net/view.php?id=295 295] - Files - Task Access security circumvented by files module (caseydk)
*  [http://bugs.web2project.net/view.php?id=297 297] - Reports - Change the select id="project_id" rendering of project info (caseydk)
*  [http://bugs.web2project.net/view.php?id=298 298] - Tasks - Cannot select contacts from mutiple companies for individual tasks (trevormorse)
*  [http://bugs.web2project.net/view.php?id=303 303] - Departments - sort by columns in the DEPARTMENT view refer to the COMPANIES page. (caseydk)
*  [http://bugs.web2project.net/view.php?id=304 304] - Projects - When updating a project to change the department, the department becomes completely unset. (caseydk)
*  [http://bugs.web2project.net/view.php?id=313 313] - Reports - .htaccess for PDF reports incorrect (caseydk)
*  [http://bugs.web2project.net/view.php?id=314 314] - Tasks - End date issue when editing task after upgrade from trunk 750 to trunk 800 (caseydk)
*  [http://bugs.web2project.net/view.php?id=316 316] - Projects - Project display (caseydk)
*  [http://bugs.web2project.net/view.php?id=317 317] - Project Designer - Javascript doesn't like apostrophe in project name (caseydk)
*  [http://bugs.web2project.net/view.php?id=323 323] - Core Infrastructure - Fresh installations of 1.1 fail (caseydk)

== Misc Changes/Improvements ==

*  Added more unit tests, not distributed with v1.2
*  Updated the system to suppress PHP 5.3 E_DEPRECATED warnings
*  Removed unnecessary code from the PHPMailer lib, the jscalendar lib, and ADODB lib
*  Added the Brazilian Portuguese translation to core
*  Converted the Projects, Companies, and Links modules to use the [[Search Hook|hook_search]] instead of the search object
*  Cleaned up some of the template generation to reduce duplication
*  Moved the mysql files around to prepare for additional multi-database support
*  Misc UI improvements including using the proper shortdate format, adding anchors to the sysval page
*  Reworked the Models and Controllers based on feedback from the CodeWorks Code Review to support a [http://blueparabola.com/blog/fat-models-are-good|"Fat Models" concept] which also moved most permissions validation from the Controllers to the Models - this is still underway, the Links module should be considered the reference implementation
*  Updated the report generation to use a randomly generated filename as opposed to an easily predictable one
*  [http://bugs.web2project.net/view.php?id=257 257] - Projects - Display of projects with sub-projects in cascade would make visibility much clearer (caseydk)
*  [http://bugs.web2project.net/view.php?id=321 321] - Files - web2project files uploading demands 777 permissions when it could do with less (caseydk)

== Open/Known Issues ==

*  The cascading dependencies are still not 100%.  Although long chains (A->B-C->D->E) work fine and tasks with multiple dependencies work fine, there are a limited number of scenarios where dependencies do not behave as expected.
**  One such scenario is when you have a Dynamic Task A with children chain (B->C-D->E) and Task F which is dependent on Task A.  If B, C, D or E shift, they shift the rest of the chain as expected and the Dynamic Task (A) as expected but unfortunately F does not get updated.
*  If you upgrade from dotProject, you may have an oddity with your default theme/display as the name has changed.  If this happens, edit your preferences, change to one of the existing themes, and save.

[[Category:Release Notes]]