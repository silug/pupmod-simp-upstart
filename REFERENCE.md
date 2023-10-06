# Reference

<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

### Classes

* [`upstart`](#upstart): This class allows you to configure the upstart init files  Unless otherwise noted, the variables passed to this class set up ``/etc/sysconfig

### Defined types

* [`upstart::job`](#upstart--job): This define allows you to manage upstart jobs in /etc/init.  See init(5) for more information. All variables lacking comments come directly f

### Functions

* [`upstart::validate_sys_limit`](#upstart--validate_sys_limit): Validate the initial system resource limits for a job's processes  See init(5) for more information.

### Data types

* [`Upstart::Console`](#Upstart--Console)
* [`Upstart::Process`](#Upstart--Process)

## Classes

### <a name="upstart"></a>`upstart`

This class allows you to configure the upstart init files

Unless otherwise noted, the variables passed to this class set up
``/etc/sysconfig/init``

This *only* sets security-relevant options. You'll need to use the augeas
provider to prod different values in the target file but this provides a good
example.

* **See also**
  * init(8)

#### Parameters

The following parameters are available in the `upstart` class:

* [`auditd`](#-upstart--auditd)

##### <a name="-upstart--auditd"></a>`auditd`

Data type: `Boolean`

If true, includes SIMP's ::auditd class and then adds upstart audit rule

Default value: `simplib::lookup('simp_options::auditd', { 'default_value' => false })`

## Defined types

### <a name="upstart--job"></a>`upstart::job`

This define allows you to manage upstart jobs in /etc/init.

See init(5) for more information.
All variables lacking comments come directly from init(5)

#### Parameters

The following parameters are available in the `upstart::job` defined type:

* [`start_on`](#-upstart--job--start_on)
* [`main_process_type`](#-upstart--job--main_process_type)
* [`main_process`](#-upstart--job--main_process)
* [`pre_start_type`](#-upstart--job--pre_start_type)
* [`pre_start`](#-upstart--job--pre_start)
* [`post_start_type`](#-upstart--job--post_start_type)
* [`post_start`](#-upstart--job--post_start)
* [`pre_stop_type`](#-upstart--job--pre_stop_type)
* [`pre_stop`](#-upstart--job--pre_stop)
* [`post_stop_type`](#-upstart--job--post_stop_type)
* [`post_stop`](#-upstart--job--post_stop)
* [`stop_on`](#-upstart--job--stop_on)
* [`default_env`](#-upstart--job--default_env)
* [`env_export`](#-upstart--job--env_export)
* [`is_task`](#-upstart--job--is_task)
* [`respawn_limit`](#-upstart--job--respawn_limit)
* [`normal_exit`](#-upstart--job--normal_exit)
* [`instance_name`](#-upstart--job--instance_name)
* [`description`](#-upstart--job--description)
* [`doc_version`](#-upstart--job--doc_version)
* [`emits`](#-upstart--job--emits)
* [`console`](#-upstart--job--console)
* [`nice`](#-upstart--job--nice)
* [`oom`](#-upstart--job--oom)
* [`chroot`](#-upstart--job--chroot)
* [`chdir`](#-upstart--job--chdir)
* [`sys_limit`](#-upstart--job--sys_limit)
* [`kill_timeout`](#-upstart--job--kill_timeout)
* [`expect_stop`](#-upstart--job--expect_stop)
* [`expect_daemon`](#-upstart--job--expect_daemon)
* [`expect_fork`](#-upstart--job--expect_fork)
* [`respawn`](#-upstart--job--respawn)
* [`author`](#-upstart--job--author)
* [`umask`](#-upstart--job--umask)

##### <a name="-upstart--job--start_on"></a>`start_on`

Data type: `String`

The set of events that will cause the job to be
automatically started.

##### <a name="-upstart--job--main_process_type"></a>`main_process_type`

Data type: `Upstart::Process`

The type of the main process, may be one of
'exec' or 'script'.

Default value: `'exec'`

##### <a name="-upstart--job--main_process"></a>`main_process`

Data type: `Optional[String]`

The content of the main process.

Default value: `undef`

##### <a name="-upstart--job--pre_start_type"></a>`pre_start_type`

Data type: `Upstart::Process`

The type of the pre-start script, may be one of
'exec' or 'script'.

Default value: `'exec'`

##### <a name="-upstart--job--pre_start"></a>`pre_start`

Data type: `Optional[String]`

The content of the pre-start stanza.

Default value: `undef`

##### <a name="-upstart--job--post_start_type"></a>`post_start_type`

Data type: `Upstart::Process`

The type of the post-start script, may be one
of 'exec' or 'script'

Default value: `'exec'`

##### <a name="-upstart--job--post_start"></a>`post_start`

Data type: `Optional[String]`

The content of the post-start stanza.

Default value: `undef`

##### <a name="-upstart--job--pre_stop_type"></a>`pre_stop_type`

Data type: `Upstart::Process`

The type of the pre-stop script, may be one of
'exec' or 'script'

Default value: `'exec'`

##### <a name="-upstart--job--pre_stop"></a>`pre_stop`

Data type: `Optional[String]`

The content of the pre-stop stanza.

Default value: `undef`

##### <a name="-upstart--job--post_stop_type"></a>`post_stop_type`

Data type: `Upstart::Process`

The type of the post-stop script, may be one of
'exec' or 'script'

Default value: `'exec'`

##### <a name="-upstart--job--post_stop"></a>`post_stop`

Data type: `Optional[String]`

The content of the post-stop stanza.

Default value: `undef`

##### <a name="-upstart--job--stop_on"></a>`stop_on`

Data type: `Optional[String]`

The set of events that will cause the job to be
automatically stopped.

Default value: `undef`

##### <a name="-upstart--job--default_env"></a>`default_env`

Data type: `Optional[String]`

Corresponds to the 'env' keyword.

Default value: `undef`

##### <a name="-upstart--job--env_export"></a>`env_export`

Data type: `Optional[String]`

Corresponds to the 'export' keyword.

Default value: `undef`

##### <a name="-upstart--job--is_task"></a>`is_task`

Data type: `Boolean`

Corresponds to the 'task' keyword.

Default value: `false`

##### <a name="-upstart--job--respawn_limit"></a>`respawn_limit`

Data type: `Optional[Array[Integer,2,2]]`

An array containing two integers corresponding to
'count' and 'interval' for the 'respawn limit' keyword.

Default value: `undef`

##### <a name="-upstart--job--normal_exit"></a>`normal_exit`

Data type: `Optional[Array[String]]`

An array of exit statuses and/or signals that
indicate tat the job has terminated successfully.

Default value: `undef`

##### <a name="-upstart--job--instance_name"></a>`instance_name`

Data type: `Optional[String]`

The 'instance' keyword.

Default value: `undef`

##### <a name="-upstart--job--description"></a>`description`

Data type: `Optional[String]`

The description of the job.

Default value: `undef`

##### <a name="-upstart--job--doc_version"></a>`doc_version`

Data type: `Optional[String]`

The jversion information about the job.  Maps to
the 'version' keyword.

Default value: `undef`

##### <a name="-upstart--job--emits"></a>`emits`

Data type: `Optional[Array[String]]`

An array of arbitrary events to emit.

Default value: `undef`

##### <a name="-upstart--job--console"></a>`console`

Data type: `Optional[Upstart::Console]`

Option to connect standard input, output, and error to
/dev/console. Value may be 'output' or 'owner'.

Default value: `undef`

##### <a name="-upstart--job--nice"></a>`nice`

Data type: `Optional[Integer]`

The process's nice value.

Default value: `undef`

##### <a name="-upstart--job--oom"></a>`oom`

Data type: `Optional[String]`

The OOM killer setting.

Default value: `undef`

##### <a name="-upstart--job--chroot"></a>`chroot`

Data type: `Optional[Stdlib::Absolutepath]`

The directory underneath which the process will be run in a chroot.

Default value: `undef`

##### <a name="-upstart--job--chdir"></a>`chdir`

Data type: `Optional[Stdlib::Absolutepath]`

The directory to be the root of the chroot instead of
the root of the filesystem.

Default value: `undef`

##### <a name="-upstart--job--sys_limit"></a>`sys_limit`

Data type: `Optional[Array[String, 3, 3]]`

Maps to the 'limit' keyword.  Accepts a three item
array of values that should be 'LIMIT','SOFT', and 'HARD' respectively.

Default value: `undef`

##### <a name="-upstart--job--kill_timeout"></a>`kill_timeout`

Data type: `Optional[Integer]`

The interval between sending the job's main process
the SIGTERM and SIGKILL signals when stopping the running job.

Default value: `undef`

##### <a name="-upstart--job--expect_stop"></a>`expect_stop`

Data type: `Boolean`

Maps to 'expect stop'.

Default value: `false`

##### <a name="-upstart--job--expect_daemon"></a>`expect_daemon`

Data type: `Boolean`

Maps to 'expect daemon'.

Default value: `false`

##### <a name="-upstart--job--expect_fork"></a>`expect_fork`

Data type: `Boolean`

Maps to 'expect fork'.

Default value: `false`

##### <a name="-upstart--job--respawn"></a>`respawn`

Data type: `Boolean`



Default value: `false`

##### <a name="-upstart--job--author"></a>`author`

Data type: `Optional[String]`



Default value: `undef`

##### <a name="-upstart--job--umask"></a>`umask`

Data type: `Simplib::Umask`



Default value: `'022'`

## Functions

### <a name="upstart--validate_sys_limit"></a>`upstart::validate_sys_limit`

Type: Ruby 4.x API

Validate the initial system resource limits for a job's processes

See init(5) for more information.

#### `upstart::validate_sys_limit(Optional[Array[String, 3, 3]] $sys_limit)`

Validate the initial system resource limits for a job's processes

See init(5) for more information.

Returns: `Any` true in validation succeeds

Raises:

* `upon` any validation failure

##### `sys_limit`

Data type: `Optional[Array[String, 3, 3]]`

3-tuple containing the limit name, soft limit, and hard limit

## Data types

### <a name="Upstart--Console"></a>`Upstart::Console`

The Upstart::Console data type.

Alias of `Enum['output', 'owner']`

### <a name="Upstart--Process"></a>`Upstart::Process`

The Upstart::Process data type.

Alias of `Enum['exec', 'script']`
