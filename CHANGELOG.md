Changelog
---------

v0.6.0
------
<em>Codename: <strong>Daring Mammoth</strong></em><br/>
<em>Release date: September 30, 2013</em>

* [New] Added a validation when removing protected FK relationships.
* [New] Added a progress info (at bottom widgets bar) for temporary model saving.
* [New] User can now restore the last session via File > Restore Session. Sessions will not be restored at startup anymore.
* [New] Added a "zoom" option when exporting to PNG image.
* [Change] Disabled the model loading via command line on MacOSX due to bundle particularities.
* [Change] Remove option "Save session" from general config widget.
* [Change] Improved the way schema's children objects are selected/unselected.
* [Change] Improved the printing operation. Now custom paper size has a separated field to assign it's coordinates.
* [Change] The import errors now are written on a log file when "ignore import errors" is checked.
* [Fix] Fixed an inconsistence when removing a table before the fk relationship linked to it. From now on (to avoid crashes) user must remove the relationship first and then remove the table.
* [Fix] Fixed a minor bug on column's graphical representation that was incorrectly configuring the column descriptor for self-relationship fk's.
* [Fix] Minor fix on model overview widget when showing large models.
* [Fix] Fixed bug on pgmodeler-cli that was generating errors when running it outside the executable's directory.
* [Fix] Fixed the calculation of pages to be printed.
* [Fix] Fixed the type enumeration validation to accept space on the names.
* [Fix] Minor fix for GiS types. Spatial auxiliary type name can null.
* [Fix] Minor pgmodeler-cli typos corrections.
* [Fix] Fixed a bug related to XMLParser and threads that was crashing pgModeler on Windows.
* [Fix] Fixes on DatabaseImportHelper to correctly handle extension created types.
* [Fix] Minor fix on PgSQLType::parseString() when creating datatypes from strings.

v0.6.0-beta
------
<em>Codename: <strong>Daring Mammoth</strong></em><br/>
<em>Release date: September 16, 2013</em>

* [New] Added experimental reverse engineering support.
* [New] Added an experimental option --fix-model to pgmodeler-cli to permit the user to fix the structure of an older model (generated in pgModeler < 0.6.0) or a corrupted file.
* [New] Added an option to debug the import process printing any generated code to stdout.
* [New] Added support for bidirectinal FK relationships.
* [New] Added a statement "SET search_path [schemas]" on database model SQL code.
* [New] Added missing PostgreSQL built-in types.
* [New] Configured connections now can be duplicated in order to reuse it's attributes.
* [Change] Minor change on main compilation script. The subproject "tests" are included only when compiling in debug mode.
* [Change] Major change on validation widget. Fixes are now applied using a thread and can be aborted any time user want.
* [Change] Change on model saving process. pgModeler will not deny to save invalidated anymore. Now it will ask the user to validate the model or save an invalidate one anyway.
* [Change] Changed the behavior of the operation list. In the first exception the entire list are emptied.
* [Change] Changed the way foreign keys are generated. They always will be generated at end of database definition to avoid reference breaking.
* [Change] Minor improvements on model code generation and copy operations.
* [Change] Removed deprecated "rtree" indexing type.
* [Fix] Minor fixes on PgSQLType class. User types aren`t removed instead they are deactivated to avoid reference breaking.
* [Fix] Minor fix on selecting the children objects of a schema.
* [Fix] Minor fixes on scene and relationship avoiding crashes when destroying the whole graphical scene.
* [Fix] Fixed bug on deleting self relationships.
* [Fix] Minor fix on model export process. The last line of the SQL code now is correctly extracted and executed.
* [Fix] Minor fix on sequence class to accept owner.
* [Fix] Minor fixes on the splash screen control code.
* [Fix] Fixed a bug that was crashing pgModeler at startup.
* [Fix] Fixed a bug that was causing pgModeler to crash when loading operators which name contained '&' char.
* [Fix] Fixed bug related to sequence values assignment.
* [Fix] Fixed "Operation with not allocated object" error on applying validation fixes.
* [Fix] Fixed relationship label position saving.
* [Fix] Minor fix on main window. pgModeler now is not closed while the validation is running.

v0.6.0-alpha1
------
<em>Codename: <strong>Daring Mammoth</strong></em><br/>
<em>Release date: August 05, 2013</em>

* [New] Added catalog query for triggers.
* [New] Added catalog query for rules.
* [New] Added indexing method to exclude constraint.
* [New] Added catalog query for constraints.
* [New] Added catalog queries for tables and columns
* [New] Added catalog queries for view, domain, sequence and user defined types.
* [New] Added catalog query for collation.
* [New] Added catalog query for operator family.
* [New] Added catalog query for operator class.
* [New] Object dependencies form now can list indirect dependencies.
* [New] Added an environment variable to set a different location for crash handler executable.
* [New] Objects that has SQL disabled now is shown with name striked out.
* [Change] Minor change on MainWindow::closeEvent()
* [Change] Moved app_style variable to GlobalAttributes::DEFAULT_QT_STYLE.
* [Change] Minor improvement on Exception::getExceptionsText method.
* [Change] Improvements on copy/paste operations.
* [Change] Removed unused linker parameters.
* [Change] Crash handler executable renamed to "pgmodeler-ch".
* [Fix] Fixed possible leak when destroying a ModelWidget instance. Objects from  scene were not being deleted correclty. Fix tests in progress.
* [Fix] Fixed the "Save current session" option on GeneralConfigWidget that wasn't doing it's job correctly.
* [Fix] Fixed a bug that was crashing pgModeler at startup when restoring previous sessions or temporary models.
* [Fix] Minor fix on trigger code generation.
* [Fix] Fixed incorrect loading of multiple triggers/rules on views.
* [Fix] Minor fix on model validation. Operator classes are now checked during the validation process.
* [Fix] Fixed generation of constraints in form of ALTER command. In some cases the constraint code wasn't appended to table's definition.
* [Fix] Minor fixes on cast object.
* [Fix] Minor fixes on databasemodel on retrieving dependencies/references for objects.
* [Fix] Fixed crash handler path variable on MacOSX.

v0.6.0-alpha
------
<em>Codename: <strong>Daring Mammoth</strong></em><br/>
<em>Release date: July 19, 2013</em>

* [New] Added the widget to swap objects IDs on model validation form.
* [New] Added indexing type "spgist" to IndexingType class.
* [New] Model validation and export now works with threads.
* [New] Functions now have a "leak proof" attribute.
* [New] VARIADIC key attribute added to function parameters.
* [New] User now can completely disabled UI stylesheets by calling executable with param "-no-stylesheet".
* [New] Added the class Catalog to handle the basis of reverse engineering by reading the pgcatalog/information_schema.
* [New] System tablespaces pg_global and pg_default are now automatically created as new models are added.
* [Change] Minor change on schema area selection. The entire schema area and children can be selected (and moved) by using "Select children" action or SHIFT + left-click.
* [Change] Improved the transition between opened models. The problem was solved putting the temporary models saving in a separated thread.
* [Change] Minor improvement on model restoration operation. Models that fails to be restored can be kept so the user can try to fix them manually (until pgModeler is closed).
* [Change] Minor adjustments on model loading progress.
* [Change] Minor chages on model export form. Export to DBMS is the default option.
* [Change] Minor improvements on pgmodeler-cli. Added "--simulate" option to export dbms.
* [Change] Disabled notice output to console for Connection class. User can re-enable it by calling Connection::setNoticeEnabled() [recompile source needed].
* [Change] Minor changes on PgSQL base types. "[NO] LEAKPROOF" removed from FunctionType class.
* [Change] Minor improvements on SchemaParser, now its possible to make parser ignore empty attributes.
* [Change] libdbconnect renamed to libpgconnector for semantics reasons.
* [Change] Minor improvements on CrashHandler. Added buttons to load report and save embedded model when in analysis mode.
* [Fix] Minor fix on linuxdeploy.sh script related to grep command execution.
* [Fix] Fixed some leaks when destroying objects that are registered as PgSQLType (table, sequence, extension, domain, view, type). Now these type are correctly remove from user type listing.
* [Fix] Fixed bad sql code generation when disabling sql of columns/constraints.
* [Fix] Fixed dependency retrieving for operator classes.
* [Fix] Fixed incorrect reference to "replicate" option on Roles.
* [Fix] Fixed the "ignore duplicity" bug for columns when exporting model.
* [Fix] Fixed library build order now libpgmodeler is built before libpgconnector.
* [Fix] Minor fix on UI stylesheet related tooltips when using Fusion theme.
* [Fix] Fixed the assignment of LC_COLLATE, LC_CTYPE and template db to database instance on DatabaseWidget.


v0.5.2
------
<em>Codename: <strong>Lovely Duda</strong></em><br/>
<em>Release date: June 27, 2013</em>

* [New] User now can append free SQL commands to database objects via "Append SQL" command.
* [New] Introduced an experimental code completion on fields that permits code input.
* [New] User can create default sequences from serial columns. This feature does not apply to columns generated by relationships.
* [New] Introduced a feature to break relationship lines in straight angles and to remove all user added points.
* [New] Added support to change font size on textboxes.
* [Change] Removed the code "OIDs=FALSE" from table's SQL.
* [Fix] Minor fix on Mac OSX deployment script.

v0.5.1_r1
---------
<em>Codename: <strong>Lovely Duda</strong></em><br/>
<em>Release date: June 13, 2013</em>

* [New] Added deployment scripts on all platforms to compile and pack pgModeler. Note: On Windows the script must run on GNU environment port like Cygwin or MingW.
* [New] Added an special field to columns to easily identify which relationship generated it. (only for columns added by relationship)
* [Change] Model overview widget is now shown always stay on top.
* [Change] Minor improvements on syntax highlighter.
* [Change] Improvements on model validation widget. Output panel now shows the currently validated object (SQL validation).
* [Fix] Removed from user defined type DTD the mandatory use of collation object.
* [Fix] Collation's SQL generation corrected. Encoding is appended to LOCALE keyword.
* [Fix] Corrected the wrongly used COLLATION keyword on user defined type.
* [Fix] Corrected a bug that was crashing pgModeler when selecting relationship created objects on object finder result list.
* [Fix] Extension object naming corrected.
* [Fix] Extension object removal corrected.
* [Fix] Corrected a bug on CLI that was not finding dependencies paths correctly.
* [Fix] Minor fix on task progress widget on MacOSX.
* [Fix] Splash screen corrected on MacOSX
* [Fix] Corrected a bug on relationships that was crashing pgModeler when specifying column name pattern.

v0.5.1
------
<em>Codename: <strong>Lovely Duda</strong></em><br/>
<em>Release date: June 1, 2013</em>

* [New] Code base ported to C++11 and Qt5.
* [New] MacOSX compilation now generates an application bundle: pgmodeler.app
* [New] pgModeler is now capable of associate dbm files to its executable being possible opening a model from file manager by clicking it (except for MacOSX, see MacOSX notes).
* [New] Added support for loading models by calling pgModeler gui executable from terminal (e.g. pgmodeler model1.dbm model2.dbm)
* [New] pgModeler logo redesign.
* [New] Added special primary keys support to one-to-one and one-to-many relationships.
* [New] Relationships now supports patterns to define generated objects names. The manual suffix and auto-suffix generation are deprecated.
* [New] Columns/constraints generated by relationship can have position changed on parent table.
* [New] Added smallserial built-in datatype.
* [Change] Improvements on model validation tool. pgModeler will not save the model while isn't completely validated.
* [Fix] minor fix on point insertion on relationships.
* [Fix] Corrected the wrongly displayed interval fields.
* [Fix] Corrected self relationship validation.
* [Fix] Corrected a bug on editing numeric data types.
* [Fix] Minor fixes on build scripts (All platforms).
* [Fix] Added the missing directive CONFIG+=console to main-cli.pro
* [Fix] Minor fixes on task progress exhibition on quick tasks.
* [Fix] pgmodeler-cli output fixed on Windows system.
* [Fix] Table inheritance now copies columns with NOT NULL attribute correclty configured.
* [Fix] Plugin build scripts fixed. Now generated libraries are correctly copied to build directory.
* [Fix] Editing a column with 'numeric' datatype does not generate errors anymore.

v0.5.0
------

<em>Release date: May 17, 2013</em>

* [New] Complete main window restyling.
* [New] Added a model validation tool to prevent reference break and name conflicts.
* [New] Added an object navigation using keyboard on model widget. Pressing Alt + [left|right] keys will switch between graphical objects.
* [New] Introduced the pgmodeler-cli. A command line tool to handle model export without loading the graphical interface.
* [New] Added an option to list available configured connections on pgmodeler-cli.
* [New] pgModeler now alerts the user when he try to save an invalidated model.
* [New] pgModeler now aborts app closing when the user wants to do a last saving on modified models.
* [New] Added support to hide relationship labels and table extended attributes on configuration dialog.
* [New] Added "Recent Models" menu.
* [New] Introduced the Xml2Object plugin to help on develpment testings.
* [New] Added partial support to PostgreSQL Extensions objects.
* [New] Added JSON datatype.
* [New] Added support for rules and trigger on views.
* [New] Added support for user defined range types.
* [New] Added support for collations on composite types (user defined).
* [New] Added built-in range types.
* [New] Added support to INCLUDING/EXCLUDING options when dealing with copy relationships.
* [New] Added support for EXCLUDE constraint support
* [New] Added NO INHERIT option to check constraints.
* [New] Added REPLICATION option to roles.
* [New] Added FOR ORDER BY option and removed Recheck from OperatorClassElement.
* [New] Added collation support for index elements.
* [New] Added [NOT] LEAKPROOF key word to functions.
* [New] Added collation attribute to domains.
* [New] Required fields are now highlighted on editing forms.
* [New] pgModeler creates system objects (e.g, public schema and SQL, C, plpgsql languages) when adding a new model.
* [Change] Minor improvements on when showing Views.
* [Change] Relationship points are moved when the parent relationship is being moved together with other objects.
* [Change] Simplified the model loading operation. pgModeler will not try to recreate objects with unsatisfied dependencies instead errors will be raised.
* [Change] Minor changes on FK relationship creation.
* [Change] User-added foreign-keys had code generation changed.
* [Change] Minor improvements on PgModelerPlugin structure.
* [Change] DummyPlugin renamed to Dummy.
* [Change] Improvements on building process for all supported systems.
* [Change] Removed "Save widget positions" from configuration form.
* [Change] Removed fullscreen mode from main window.
* [Change] Removed unused/deprecated error messages.
* [Change] Removed deprecated files COMPILING.md and PLUGINS.md.
* [Change] Subproject libutil was renamed to libutils due to some conflicts on Linux systems.
* [Change] Startup scripts removed. Since the environment variables are set by the installer on Windows and for Unix the variables are set using the new pgmodeler.sh script.
* [Change] "Disable SQL code" option added for all types of objects. Except for textboxes and base relationships (view-table relatioships and fk relationships).
* [Change] Fixed permissions for views.
* [Change] PostgreSQL 8.x support completely removed.
* [Change] Schema files (for SQL code) aren't organized in folders anymore. All code (for different PostgreSQL versions) will be in the same .sch file for each object.
* [Change] Spatial types had SRID digit count upgraded to 5.
* [Change] One-to-one relationships now generates unique names for UNIQUE constraints.
* [Change] Several class improvements, performance tunings and forms readjustments.
* [Fix] Minor fixes on connection configuration form.
* [Fix] Corrected a bug that was crashing pgModeler when adding new schemas.
* [Fix] Corrected a bug that was crashing pgModeler when validation model.
* [Fix] Corrected a bug that was preventing the popup menu to be configured correctly on model widget.
* [Fix] Menu bar style correctly applied on Windows system.
* [Fix] Now relationship labels' position are restored when loading the model file.
* [Fix] Minor fixes on database model code generation.
* [Fix] Corrected the glicthy wheel scroll/zoom on model widget.
* [Fix] Corrected the visual update of schema's rectangle when adding a column on a child table.
* [Fix] Corrected a bug that was preventing a new model to be saved correctly.
* [Fix] Minor fixes on model widget copy/paste operations.
* [Fix] Models now are correclty auto saved when modified.
* [Fix] Corrected operator's signature generation.
* [Fix] Corrected a bug on textbox with unicode texts.
* [Fix] Index and Rule editing forms now handles correctly unicode expressions.
* [Fix] Corrected a bug that was avoiding the name "remembering" during relationship loading.

v0.4.1_r1
---------

<em>Release date: March 19, 2013</em>

* [Change]: user can now prepend a CTE (commom table expression, a.k.a "with queries") on view's definition.
* [Change]: user can now create a single reference containing a expression that defines the entire view.
* [Change]: improvements on permissions, user now can control GRANTs and REVOKEs via permission editing form.
* [Fix]: fixed invalid UTF-8 chars on function definition.
* [Fix]: fixed unavailable "nocreatedb" role option.

v0.4.1
------

<em>Release date: March 16, 2013 </em>

* [New]: introduced the  "Disable SQL code" option for roles/tablespaces.
* [New]: user now can add objects by right-clicking group items on "Model Objects" dockwidget tree.
* [New]: added the abbreviation for time and timesptamp data types both with timezone: timetz and timestamptz.
* [New]: introduced a object highlight action on "model objects" dockwidget.
* [Change]: major changes on SQL code generation/export. Introduced a token to help export process to identify the end of each DDL command.
* [Change]: minor improvements on role editing form.
* [Change]: when generationg XML code empty tags that stores pure texts are now created with a <![CDATA[]]> tag in order to avoid malformed xml code.
* [Change]: index FASTUPDATE and FILLFACTOR params is now activated according the indexing type.
* [Change]: index fill factor now is optional.
* [Change]: chinese, portuguese and french translations update.
* [Fix]: pgModeler no longer crash when in error state (showing an exception) and try to auto save the models.
* [Fix]: minor size adjustments on forms.
* [Fix]: corrected a bug related to one-to-many relationship validation (endless looping) when changing to automatic suffix generation.
* [Fix]: corrected the "apply button disabled" bug on constraint edit form.
* [Fix]: IN/OUT keywords now appears on functions signature.
* [Fix]: corrected translation bypassing on index edit form.
* [Fix]: pgModeler no longer crash when triggering the print action.
* [Fix]: triggers no longer complains about assigning a function without parameters.
* [Fix]: corrected the loading process for indexes.
* [Fix]: corrected some bugs related to GiST and index sorting.
* [Fix]: minor fix on quick rename action when renaming a column with primary key.
* [Fix]: corrected a bug that was causing pgModeler to complain about duplicated elements when loading indexes.
* [Fix]: corrected a bug related to main window title when save a model with a different filename.
* [Fix]: fixed a bug related reload a model file after editing a foreign key.
* [Fix]: corrected a bug related to invalid chars at task progress.

v0.4.0_r1
---------

<em>Release date: March 04, 2013 </em>

* [New]: introducing the "pgModeler Wiki" as the main project's support resource.
* [Fix]: when main windows is closed the overview widget is closed too.
* [Fix]: corrected a bug on operation list widget that was converting an item name to UTF-8 twice.

v0.4.0
------

<em>Release date: February 27, 2013 </em>

* [New]: introduce a "New object" submenu when activating the schema context menu (right-click)
* [New]: tables and view are now graphically separated by colored rectangles representing its schemas.
* [New]: compiling pgModeler now works perfectly on Mac OSX system.
* [New]: introduced the 'Quick actions' menu that permits: rename, move to another schema, change onwer and edit permissions.
* [New]: the relationship editing form gained an "advanced" tab which shows the objects generated and/or represents the relatioship itself.
* [New]: the user now can add relationships only creating foreign keys on tables (fk relationships).
* [New]: added a french UI translation (provided by [toorpy](https://github.com/toorpy)).
* [Change]: all relationships type are now grouped together on "Model objects" widget.
* [Change]: chinese UI translation updated (provided by: [Bumanji](https://github.com/Bumanji)).
* [Change]: user now can remove fk relationships directly without needing to remove the related foreign keys.
* [Change]: field semantics adjustments on relationship editing form.
* [Change]: graphical object can be now selected and have the context menu activated only with a single right-click.
* [Change]: minor improvements on plugin base class: PgModelerPlugin.
* [Change]: widget size adjustments to better showing on Mac OSX system.
* [Change]: crashhandler now shows the compiled and running versions of Qt.
* [Change]: french UI translation reviewed and updated (provided by [babs](https://github.com/babs)).
* [Change]: 'Objects of Model' when used as object picker now expand all the nodes by default.
* [Change]: 'Objects of Model' now memorizes the tree state when update an object and / or opening another model.
* [Change]: PostGiS 'geometry' type can have a free assigned SRID value.
* [Change]: editing forms when shown set the focus on the first field, generally, the object name.
* [Change]: 'Objects of Model' widget displays the nodes in alphabetical order.
* [Change]: the printing options for the model were moved to the general configuration form.
* [Change]: relationship validation method now removes fk relationships when the foreign keys that gerenates is no longer exists.
* [Change]: copy/cut/delete commands does not manipulates system objects like schema public and languages C, SQL and plpgsql.
* [Change]: pgModeler startup scripts are now path location free meaning that software can be installed where the user desires.
* [Fix]: corrected a bug related  constraint name on domain XML code generation.
* [Fix]: corrected a bug that was causing crash when click "Apply" on Type editing form with fields not filled.
* [Fix]: corrected the "invalid constraint name" error on domain editing form.
* [Fix]: corrected the empty DEFAULT clause for columns, types and domains.
* [Fix]: corrected a bug related to incorrectly initialized OID attribute when creating tables.
* [Fix]: corrected a bug when creating a view with WHERE statement.
* [Fix]: corrected a bug related to one-to-many relationships semantics.
* [Fix]: corrected some bugs that was causing crash when removing all operations from operation list.
* [Fix]: minor bug fixes related to object selection over the model.
* [Fix]: corrected a bug on load model dialog filter (chinese UI only).
* [Fix]: pgModeler no longer crash when editing objects style.
* [Fix]: corrected bug that was deleting two sequeces at once.
* [Fix]: pgModeler no longer crash when removing (disconnecting) relationship that has special primary keys.
* [Fix]: minor fixes on the startup scripts on all platforms.
* [Fix]: corrected an incorrect reference to output stream on Windows system.
* [Fix]: shortcuts and popup menu now works correctly when selection an object on 'Objects of Model' tree.
* [Fix]: the pgsql base types (represented by tables, sequences, user defined types and domains) are now updated correctly when the related schema is renamed.
* [Fix]: corrected some weird SRID value on non spatial types.
* [Fix]: corrected bug on objects table when move rows to last / first.
* [Fix]: typos corrections on some error messages and dialog titles.
* [Fix]: 'referenced columns' combobox on constraint editing form are filled correctly when the dialog is shown in a second time.
* [Fix]: pgModeler no longer crash when creating many-to-many relationships.
* [Fix]: pgModeler no longer crash when the user activates the print dialog.
* [Fix]: corrected bug that was removing fk relationships when pasting objects.
* [Fix]: corrected SQL syntax error of 'timestamp with time zone'.
* [Fix]: corrected constraint type showing on editing form.
* [Fix]: corrected bug on cyrillic typed enums and check constraints expressions.
* [Fix]: corrected bug on enumeration type editing form.
* [Fix]: corrected bug on 'truncate' table privilege code generation.
* [Fix]: corrected column default value code generation.
* [Fix]: dummyplugin build process corrected on Windows.
* [Fix]: corrected bug on column comment code generation.
* [Fix]: corrected bug that was deleting two tables at once.

v0.3.4
------

<em>Release date: October 17, 2012</em>

* [New]: added chinese UI translation (provided by [gjunming](https://github.com/gjunming)).
* [New]: added basic support for PostGiS 2.0 only data types: box2d, box3d, geometry and geography (suggested by [george-silva](https://github.com/george-silva) on [issue#28](https://github.com/pgmodeler/pgmodeler/issues/28))(EXPERIMENTAL). Note: when using these data types make sure that PostGiS extension is installed on database cluster since pgModeler WILL NOT install it automatically or generate the command to do it!
* [New]: added a model restoration feature to reopen models after unexpected quit (crash).
* [New]: added a crash handler to pgModeler. Now signal SIGSEGV is trapped (in most cases) and the crash handler pops up permiting the user to generate an error report. (EXPERIMENTAL)
* [New]: to facilitate the error reporting exceptions stack now can be showed in text format. Users can post the complete error stack when creating an issue.
* [New]: icon added to pgModeler executable (Windows only)
* [Change]: update on pt_BR translation file.
* [Change]: removed "pgmodeler" prefix from translation files.
* [Change]: added the field "Underline" on textbox editing form.
* [Fix]: corrected the "AlwayOnTop" bug on model overview widget. ([issue#30](https://github.com/pgmodeler/pgmodeler/issues/30))
* [Fix]: little fix on startup scripts. Corrected de PGMODELER_ROOT on both Linux and Windows systems. ([issue#29](https://github.com/pgmodeler/pgmodeler/issues/29))
* [Fix]: corrected the referece to environment variables PGMODELER_*. Now pgModeler search for necessary paths on current directory if some of these variables are not set.
* [Fix]: corrected the validation of UTF-8 names that have 3 bytes length.
* [Fix]: corrected the sources path reference on project (.pro) files. Now lupdate command do not generates empty TS files.
* [Fix]: corrected a bug that was causing crash where user try to edit protected objects.
* [Fix]: corrected the exhibition of UTF-8 messages on ```throw``` statements.

v0.3.3
------

<em>Release date: October 09, 2012</em>

* [Change]: pgModeler license were update to GPLv3.
* [Change]: Error massages and entire UI were translated to en_US. Now people can contribute more easily with translation files. [(issue#8)](https://github.com/pgmodeler/pgmodeler/issues/8)
* [Change]: The left side image were removed form all forms giving more space to show widgets.
* [Change]: pgModeler now shows a messagebox at startup if any critical error is raised instead to show them on stdin.
* [Fix]: Translation files now are correctly loaded depending on system language. [(issue#23)](https://github.com/pgmodeler/pgmodeler/issues/23)
* [Fix]: Compilation process and execution is working correctly on Windows system. [(issue#11)](https://github.com/pgmodeler/pgmodeler/issues/11)
* [Fix]: No more crashes when dealing with relationships that have special triggers/indexes/columns. [(issue#8)](https://github.com/pgmodeler/pgmodeler/issues/8) [(issue#24)](https://github.com/pgmodeler/pgmodeler/issues/24)

v0.3.2
------

<em>Release date: September 27, 2012</em>

* [Change]: The default extension for the models now stands for ".dbm" [(issue#9)](https://github.com/pgmodeler/pgmodeler/issues/9)
* [Change]: Tables and sequences now can be used as function return type as well parameter type. This is valid for other objects that make use of base types (except for table columns).
* [Change]: The relationship conversion command now need to be confirmed by the user.
* [Fix]: Compilation process now works correctly on Windows system.
* [Fix]: Adjusted the size of some forms to show their fields properly.
* [Fix]: The "make distclean" command now make the correct cleanup on build/ directory.
* [Fix]: Startup scripts "start-pgmodeler.(sh|bat)" where adjusted. To prevent errors pgModeler need to be started through these scripts.
* [Fix]: Corrected the reference to the plugins directory. [(issue#7)](https://github.com/pgmodeler/pgmodeler/issues/7)
* [Fix]: The action "New Object -> Tablespace" now is displayed properly.

v0.3.1
------

<em>Release date: September 18, 2012</em>

* [New]: Relationships generates column suffixes automaticaly. This behavior can be changed on the relationship editing form.
* [New]: Added two samples to pgModeler.
* [Change]: Tables are now created with "With OIDs" attribute by default.
* [Change] The graphical update method on overview widget has improved preventing unecessary processing.
* [Fix]: Class CenaObjetos now doesn't delete objects twice.
* [Fix]: Eliminated bug that caused crashing on pgModeler when closing a model.

v0.3.0
------

<em>Release date: September 12, 2012</em>

* [New]: Added a model overview widget.
* [New]: Added export feature that generates PNG image of the models.
* [Fix]: Corrected the naming of columns generated by many-to-many relationships.
* [Fix]: Corrected generation of XML/SQL code by the model.

v0.2.0
------

<em>Release date: August 31, 2012</em>

* [New]: Added an interface to implement third party plugins. Check [PLUGINS.md] (https://github.com/pgmodeler/pgmodeler/blob/master/PLUGINS.md) for details.
* [New]: Added a short cut to easily control the zoom on the model. Use Crtl + Mouse wheel up (zoom up) or Crtl + Mouse wheel down (zoom down).
* [Change]: Due to the plugin interface the compilation method changed back to the form of shared libraries + executable.
* [Fix]: No more crashes when removing an primary-key of a table which has relationship with other tables. [(issue#2)](https://github.com/pgmodeler/pgmodeler/issues/2)
* [Fix]: Adjusted the semantics of one-to-one relationships.

v0.1.2
------

<em>Release date: August 24, 2012</em>

* [New]: Added a functionality to save modified models before closing the software.
* [Change]: Updated the en_US dictionary with the texts of the above functionality.
* [Fix]: Dockwidgets no longer disappear unexpectedly when the main window is minimized.
* [Fix]: Operations performed before creating a table object (column, constraint, trigger, index, rule) are no longer removed when any exception is thrown in the creation of these object.
* [Fix]: Fixed bug that caused user-defined types had wrong SQL/XML code generated by the model.
* [Fix]: Functions and Types received an own range of id in order to create these objects in a correct way.
* [Fix]: Eliminated segmentation faults caused by the destruction of relationships which possessed attributes/constraints.
* [Fix]: Adjusted the translation to SQL code of one-to-one relationships.
* [Fix]: Eliminated segmentation fault when editing relationships and/or undoing an operation involving a relationship.
* [Fix]: Identifiers relationships now correctly display the thick line beside the weak entity.

v0.1.1
------

<em>Release date: August 14, 2012</em>

* [Fix]: Correction of the actions for inserting graphic objects (table, text box, vision and relationship) in Windows environment.
* [Fix]: Correction on the display of the maximize button in the window decoration in Windows environment.
* [Fix]: Adjust on the position and spacing of widgets in editing forms.
* [Fix]: The XML parser can now correctly read DTD files in Windows environment.
* [Fix]: The compilation method is no longer in the form of shared libraries + executable and passed to be as standalone executable only.

v0.1.0
------

<em>Release date: August 9, 2012</em>

* First pgModeler release.
