<!-- .slide: data-state="normal" id="kanku-beginning" data-menu-title="Beginning with kanku" -->
## Beginning with kanku

<div
  style="display:flex;"
>
<div
  style="display:table-cell;vertical-align:top;width: 50%;"
>
  <ul>
    <li>Installation</li>
    <li>Read the docs</li>
    <li>Setup Host System</li>
    <li>First Project - Basic Job</li>
    <li>Check out our examples</li>
    <li>Basic concepts of kanku</li>
    <li>Create and use your first image in kanku</li>
  </ul>
</div>
<div
  style="display:table-cell;vertical-align:top;width: 50%;text-align: right;"
>
<img 
  alt="Kanku Developer Mode Overview" 
  src="images/kanku-logo/kanku-tech-dev-mode.png"
/>
</div>
</div>


<!-- .slide: data-state="normal" id="kanku-installation" data-menu-title="Kanku Installation" -->
## Installation

### Add repositories

```none
su -
zypper ar obs://devel:kanku:perl devel:kanku:perl
zypper ar obs://devel:kanku devel:kanku
```

### Refresh local repository cache

```none
zypper ref -s
```

### Install kanku packages

```none
zypper in kanku sudo

```

### For ubuntu users

https://raw.githubusercontent.com/M0ses/kanku/master/KankuFile.kanku-ubuntu

(SEE section ExecuteCommandsViaSSH)



<!-- .slide: data-state="normal" id="kanku-docs" data-menu-title="Kanku Documentation" -->
## Read the docs

```
# Overview of kanku commands
kanku --help
```
```
# Command specific parameters 
kanku <command> --help 
```
```
# Overview of all Handlers
perldoc Kanku::Handler
```
```
# Documentation of specific Handler 
#  (options, context getters/setters)
perldoc Kanku::Handler::*
```


<!-- .slide: data-state="normal" id="kanku-setup-devel" data-menu-title="Kanku Setup (Developer Mode)" -->
## Setup Developer Mode

```none
sudo /usr/bin/kanku setup --devel
sudo reboot
```


<!-- .slide: data-state="normal" id="kanku-init" data-menu-title="Kanku Initialize Project" -->
# Initial setup of your Project

<img 
  alt="Kanku Developer Mode Overview" 
  src="images/developer-mode.svg"
/>

```none
mkdir myNewProject
cd myNewProject
kanku init --memory 1024 --vcpu 1
```


<!-- .slide: data-state="normal" id="kanku-init" data-menu-title="Kanku Initialize Project" -->
# Conference Setup

`ATTENTION:` Because of limited bandwith at the conference you should change the following settings in your KankuFile:

## FIXME - Add proper urls
```
  -
    use_module: Kanku::Handler::OBSCheck
    options:
      api_url: https://osc19.kanku.local/public # FIXME
      download_url: https://osc19.kanku.local/... #FIXME
      ...
```


<!-- .slide: data-state="normal" id="kanku-init" data-menu-title="Kanku Initialize Project" -->

# Start your first kanku VM

```
kanku up
```


<!-- .slide: data-state="normal" id="kanku-examples" data-menu-title="Kanku Example Job Files" -->
# Check out our examples

[KankuFile.examples](https://github.com/M0ses/kanku/tree/master/KankuFile.examples)

```
# Example KankuFiles (Job definitions)
git clone https://github.com/M0ses/kanku
cd kanku/KankuFile.examples
```
