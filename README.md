# Puppet Bolt Node Execution / File Copier Plugins

This plugin provides a node-executor and file-copier using Puppet Bolt. Use this plugin if you want to access remote servers using [Puppet Bolt](https://puppet.com/products/puppet-bolt) command.


## Plugin Configuration Properties

* Prototol: Set protocol of the remote node. The options are SSH or WINRM (windows hosts) 
* Password Authentication (using key storage).
* Dry run? If set true, just print the command invocation that would be used but do not execute the command. This is useful to preview.

## Dry run mode

You can configure the plugin to just print the invocation string to the console. This can be useful when defining the configuration properties.


## Configuration

The plugin can be configured as a default node executor and file copier on a Project. Use the Simple Conguration tab to see the configuration properties. 

Also you can define the configuration at node level, setting the node-executor and file-copier attributes, for example:

```
<node name="LinuxNode" 
	   description="Remote Linux SSH Node" 
	   tags="Linux" 
	   node-executor="bolt-executor"
	   file-copier="bolt-file-copier"
	   hostname="192.168.0.1" 
	   osArch="x86_64" 
	   osFamily="Linux" 
	   osName="Centos 7" 
	   username="rundeckuser" 
	   bolt-protocol="ssh"
	   bolt-password-storage-path ="keys/node/linux.password" />

<node name="Windows" 
	   description="Remote Windows Node" 
	   tags="Windows" 
	   node-executor="bolt-executor"
	   file-copier="bolt-file-copier"
	   hostname="192.168.0.2" 
	   osArch="x86_64" 
	   osFamily="windows" 
	   osName="Microsoft Windows Server 2012 R2 Standard"
	   username="rundeckuser" 
	   bolt-protocol="winrm"
	   bolt-password-storage-path ="keys/node/windows.password" />
```
