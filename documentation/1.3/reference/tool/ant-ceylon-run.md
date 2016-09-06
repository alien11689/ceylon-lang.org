---
layout: reference13
title_md: '`<ceylon-run>` Ant task'
tab: documentation
unique_id: docspage
doc_root: ../../..
gh_editable: false
---

<!-- this file was auto-generated by com.redhat.ceylon.tools.antdoc.CeylonAntTaskDocTool -->

# #{page.title_md}

## Usage

**Note**: You must [declare the tasks with a `<typedef>`](../ant).

-To execute the `com.example.foo.lifecycle.start` top level method in
version 1.1 of module `com.example.foo` residing
in the `build` directory (repository):

<!-- lang: xml -->
    <target name="execute" depends="ceylon-ant-taskdefs">
      <ceylon-run run="com.example.foo.lifecycle.start"
        module="com.example.foo/1.1">
        <rep url="build"/>
      </ceylon-run>
    </target>


## Description

Executes a Ceylon program

The `<ceylon-run>` ant task wraps the [`ceylon run`](../ceylon/subcommands/ceylon-run.html) command.

### Attributes

<table class="ant-parameters">
<tbody>
<tr>
<th>Attribute</th>
<th>Description</th>
<th>Required</th>
</tr>
<tr id="attribute-module">
<td><code>module</code></td>
<td><p>The name and optional version of the module to run</p>
</td>
<td>Yes</td>
</tr>

<tr id="attribute-autoExportMavenDependencies">
<td><code>autoExportMavenDependencies</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--auto-export-maven-dependencies"><code>--auto-export-maven-dependencies</code></a> command line option.
When using JBoss Modules (the default), treats all module dependencies between Maven modules as shared.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-cacheRep">
<td><code>cacheRep</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--cacherep"><code>--cacherep</code></a> command line option.
Specifies the folder to use for caching downloaded modules. (default: <code>~/.ceylon/cache</code>)</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-compile">
<td><code>compile</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--compile"><code>--compile</code></a> command line option.
Determines if and how compilation should be handled. Allowed flags include: <code>never</code>, <code>once</code>, <code>force</code>, <code>check</code>.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-config">
<td><code>config</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--config"><code>--config</code></a> command line option.
Specifies the configuration file to use for this tool. (default: <code>./.ceylon/config</code>)</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-cwd">
<td><code>cwd</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--cwd"><code>--cwd</code></a> command line option.
Specifies the current working directory for this tool. (default: the directory where the tool is run from)</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-errorProperty">
<td><code>errorProperty</code></td>
<td><p>The ant property to set to true in the event of an error</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-executable">
<td><code>executable</code></td>
<td><p>The location of the ceylon executable script.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-failOnError">
<td><code>failOnError</code></td>
<td><p>Whether an error in executing this task should fail the ant build</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-flatClasspath">
<td><code>flatClasspath</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--flat-classpath"><code>--flat-classpath</code></a> command line option.
Launches the Ceylon module using a flat classpath.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-fork">
<td><code>fork</code></td>
<td><p>Whether the task should be run in a separate VM (default: <code>true</code>).</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-inheritAll">
<td><code>inheritAll</code></td>
<td><p>Whether a task should inherit environment and properties. Only applies when <code>forked == true</code>.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-linkWithCurrentDistribution">
<td><code>linkWithCurrentDistribution</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--link-with-current-distribution"><code>--link-with-current-distribution</code></a> command line option.
Link modules which were compiled with a more recent version of the distribution to the version of that module present in this distribution (1.2.2). This might fail with a linker error at runtime. For example if the module depended on an API present in the more recent version, but absent from 1.2.2. Allowed arguments are upgrade, downgrade or abort. Default: upgrade</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-noDefaultRepositories">
<td><code>noDefaultRepositories</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--no-default-repositories"><code>--no-default-repositories</code></a> command line option.
Indicates that the default repositories should not be used.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-offline">
<td><code>offline</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--offline"><code>--offline</code></a> command line option.
Enables offline mode that will prevent connections to remote repositories.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-overrides">
<td><code>overrides</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--overrides"><code>--overrides</code></a> command line option.
Specifies the XML file to use to load module overrides. See http://ceylon-lang.org/documentation/current/reference/repository/maven/ for information. <em>Experimental</em>.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-resultProperty">
<td><code>resultProperty</code></td>
<td><p>The ant property to set to the Ceylon program exit code</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-run">
<td><code>run</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--run"><code>--run</code></a> command line option.
Specifies the fully qualified name of a toplevel method or class with no parameters. The format is: <code>qualified.package.name::classOrMethodName</code> with <code>::</code> acting as separator between the package name and the toplevel class or method name.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-stacktraces">
<td><code>stacktraces</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--stacktraces"><code>--stacktraces</code></a> command line option.
If an error propagates to the top level tool, print its stack trace.</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-sysRep">
<td><code>sysRep</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--sysrep"><code>--sysrep</code></a> command line option.
Specifies the system repository containing essential modules. (default: <code>$CEYLON_HOME/repo</code>)</p>
</td>
<td>No</td>
</tr>

<tr id="attribute-verbose">
<td><code>verbose</code></td>
<td><p>Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--verbose"><code>--verbose</code></a> command line option.
Produce verbose output. If no <code>flags</code> are given then be verbose about everything, otherwise just be verbose about the flags which are present. Allowed flags include: <code>all</code>, <code>loader</code>, <code>cmr</code>.</p>
</td>
<td>No</td>
</tr>

</tbody>
</table>

### Nested elements

#### `<arg>`

<p>An argument to be passed to the module</p>
<table class="ant-elements">
<tbody>
<tr>
<th>Element</th>
<th>Description</th>
<th>Required</th>
</tr>
<tr>
<td><code>value</code></td>
<td><p>A command line argument to be passed to the module.</p>
</td>
<td>No</td>
</tr>
</tbody>
</table>

#### `<define>`

<p>A <code>&lt;define&gt;</code> element is used to set system properties for the ant task being executed.
Equivalent to the <a href="../ceylon/subcommands/ceylon-run.html#option--define"><code>--define</code></a> command line option.
Set a system property</p>
The value for the system property can either be passed as a `value` attribute:

    <define key="org.example.helloworld.greeting" value="Hi"/>

or it can be the text between the begin and end tags:

<!-- lang: xml -->
    <define key="org.example.helloworld.greeting">Hi</define>

Alternatively, it is posible to dispense with the attributes and use the syntax

    <define>org.example.helloworld.greeting=Hi</define>


<table class="ant-elements">
<tbody>
<tr>
<th>Element</th>
<th>Description</th>
<th>Required</th>
</tr>
<tr>
<td><code>key</code></td>
<td><p>The property to be defined</p>
</td>
<td>No</td>
</tr>
<tr>
<td><code>value</code></td>
<td><p>The value of the define</p>
</td>
<td>No</td>
</tr>
</tbody>
</table>

#### `<rep>`

<p>A module repository containing dependencies. Can be specified multiple times. Defaults to <code>&lt;rep url="./modules"/&gt;</code>.</p>
<table class="ant-elements">
<tbody>
<tr>
<th>Element</th>
<th>Description</th>
<th>Required</th>
</tr>
<tr>
<td><code>url</code></td>
<td><p>The URL or path of the module repository.</p>
</td>
<td>Yes, unless a `refid` is given</td>
</tr>
<tr>
<td><code>refid</code></td>
<td><p>A reference to a <code>&lt;rep&gt;</code> defined outside this task.</p>
</td>
<td>No</td>
</tr>
</tbody>
</table>

#### `<reposet>`

<p>A set of module repositories containing dependencies. Can be specified multiple times. Default to <code>modules</code>.</p>
A `<reposet>` element contains a number of `<repo>` and/or `<reposet>` elements. It can be defined at the top level, and then used by reference using the `refid` attribute so you don't have to repeat the same list of repositories all the time.

<table class="ant-elements">
<tbody>
<tr>
<th>Element</th>
<th>Description</th>
<th>Required</th>
</tr>
<tr>
<td><code>refid</code></td>
<td><p>A reference to a <a href="../ant/#_reposet"><code>&lt;reposet&gt;</code></a> defined elsewhere.</p>
</td>
<td>No</td>
</tr>
</tbody>
</table>


## See also

* How to [declare the tasks with a `<typedef>`](../ant).