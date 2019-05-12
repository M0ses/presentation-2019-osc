<!-- .slide: data-state="normal" id="overview" data-menu-title="Overview" -->
## Basic kanku concepts

* Jobs
* Tasks
* Kanku::Handler


<!-- .slide: data-state="normal" id="jobs-intro" data-menu-title="Job (Details)" -->
## Jobs

<img
  alt="Job stripped image"
  src="images/job-stripped.svg"
  style="float: right; height: 50%;"
/>

* A set of one or more Tasks
* loose coupling of Tasks
* JobContext for "communication" between Tasks 
  * K::H::OBSCheck -&gt; K::H::ImageDownload (download_url)
  * K::H::ImageDownload -&gt; K::H::CreateDomain (vm_image_file)
  * K::H::PrepareSSH -&gt; K::H::ExecuteCommandViaSSH (ip)


<!-- .slide: data-state="normal" id="tasks-intro" data-menu-title="Job (Tasks Details)" -->
## Tasks

<img
  alt="Job stripped image"
  src="images/job-stripped.svg"
  style="float: right; height: 50%;"
/>

* Uses exactly one Kanku::Handler and defined options
* Will be executed once
* multiple distribution modes 
  * master only
  * worker only
  * all servers


<!-- .slide: data-state="normal" id="handler-intro" data-menu-title="Kanku::Handler" -->
## Kanku::Handler classes

<img
  alt="Tasks stripped image"
  src="images/tasks-stripped.svg"
  style="float: right; height: 35%;position: fixed;right: 1%;top: 1%;"
/>

* Requires three methods
  * prepare
  * execute
  * finalize
* Might have getters/setters to modify JobContext
  * Documented in POD

```
perldoc Kanku::Handler # Overview of all Handlers
perldoc Kanku::Handler::* # Docs of options and context getters/setters
```
