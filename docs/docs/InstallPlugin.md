#  Install Couchbase Plugin


[Prerequisites](#prerequisites)

[How To install plugin](#provision-vdb)

 
 
Prerequisites
=============

-   Install delphix engine 5.3.x and above

-   Install couchbase binaries on source, staging and target servers


Install Couchbase Plugin
========================

Using GUI:
----------

1. Click on Manage and then Plugins

![](images/image2.png)

2. Click on `+` icon

![](images/image3.png)

3. Click on Upload or Upgrade a plugin

![](images/image4.png)

4. Select the `build(artifacts.json)` 

![](images/image5.png)

5. Click on close button

![](images/image6.png)

6. See the plugin version in `Plugins` section

![](images/image7.png)


Using dvp command:
-----------------
 `dvp upload -e <Delphix_Engine_Name> -u <username> --password <password>`
