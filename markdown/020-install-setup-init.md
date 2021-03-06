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
## Installation (on openSUSE)

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


<!-- .slide: data-state="normal" id="kanku-installation-ubuntu" data-menu-title="Kanku Installation on Ubuntu" -->
## Installation for ubuntu users

https://raw.githubusercontent.com/M0ses/kanku/master/install_ubuntu.sh

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
kanku init --memory 1G --vcpu 1 --domain_name my-new-project
```


<!-- .slide: data-state="normal" id="kanku-init" data-menu-title="Kanku Initialize Project" -->
# Conference Setup

`ATTENTION:` Because of limited bandwith at the conference you should change the following settings in your KankuFile:

```
  -
    use_module: Kanku::Handler::OBSCheck
    options:
      api_url: https://obs.osc19.local/public
      base_url: http://obs.osc19.local:82
      ...
```

## Import the ssl certificate for obs.osc19.local
```
su -c "curl http://obs.osc19.local/obs.crt > /etc/pki/trust/anchors/obs.pem"
update-ca-certificates
```


<!-- .slide: data-state="normal" id="kanku-init" data-menu-title="Kanku Initialize Project" -->

# Start your first kanku VM

```
kanku up [--skip_all_checks]
```

Note:
* explain 
  * shared directory
  * interaction with OBS


<!-- .slide: data-state="normal" id="kanku-examples" data-menu-title="Kanku Example Job Files" -->
# Check out our examples

[KankuFile.examples](https://github.com/M0ses/kanku/tree/master/KankuFile.examples)

```
# Example KankuFiles (Job definitions)
git clone https://github.com/M0ses/kanku
cd kanku/KankuFile.examples
```
