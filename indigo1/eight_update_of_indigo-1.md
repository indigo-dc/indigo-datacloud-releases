# Eighth Update of INDIGO-1 - 01.03.2017

The Eight Update of INDIGO-1 release contains:
*
* [Infrastructure Manager v1.5.1](#im)
* [Nova-Docker v. 13.0.0](#nd)
* [rOCCI_cli v. 3.4.9](#roc)



## <a name="im"></a>Infrastructure Manager v 1.5.1

#### What's new
* The updated version of the IM provides several bugfixes and improvements like:
  * Fix Error saving TOSCA data
  * Improve load data.
  * Fix Bug in IM in HA mode getting old data.
  * Bootstrap ansible master VM with python if it does not have it installed.
  * Fix Error configuring VMs with sudo with password.
  * Fix errors in EC2, GCE and OCCI connectors.
  * Update OpenNebula to new TTS API


#### List of RfCs

* Error in GCE connector in case of multiples nodes: https://github.com/grycap/im/issues/161
* OCCI conn must provide ID of the storage and storagelinks: https://github.com/grycap/im/issues/249
* Add new timeout config value for SSH access: https://github.com/grycap/im/issues/244
* Error getting provider_id in case that is not specified in the first net: https://github.com/grycap/im/issues/240
* Check REST API compatibility with new versions of CherryPy: https://github.com/grycap/im/issues/219
* Update EC2 instance types to new ones: https://github.com/grycap/im/issues/226
* Improve Error Message for InvalidParameterCombination: https://github.com/grycap/im/issues/228
* Error in OCCI connection getting VM ID in some OpenStack sites: https://github.com/grycap/im/issues/236
* Error in OCCI connector on start or stop VMs: https://github.com/grycap/im/issues/234
* Issue in GCE that removes last line in authorized_keys: https://github.com/grycap/im/issues/229
* SSL Error in OCCI conector: https://github.com/grycap/im/issues/223
* Improve load data: https://github.com/grycap/im/issues/200
* Bug in IM in HA mode getting old data: https://github.com/grycap/im/issues/210
* Incorrect error message in case of error deleting a SG in EC2 conn: https://github.com/grycap/im/issues/208
* Error configuring VMs with sudo with password: https://github.com/grycap/im/issues/204
* InvalidPermission.Duplicate when opening ports for TOSCA Template: https://github.com/grycap/im/issues/203
* Bootstrap ansible master VM with python if it does not have it installed: https://github.com/grycap/im/issues/201
* Merge correctly local /etc/hosts with IM generated data enhancement: https://github.com/grycap/im/issues/199
* Weird error when not specifying image information to an IM in single-site mode: https://github.com/indigo-dc/im/issues/157
* Enable to use TOSCA functions in all sections: https://github.com/indigo-dc/im/issues/149
* Error trying to decode OIDC auth token: https://github.com/indigo-dc/im/issues/154
* Update OpenNebula to new TTS API: https://github.com/indigo-dc/im/issues/145
* Add Ctxt log attribute for INDIGO Compute node: https://github.com/indigo-dc/im/issues/144
* DependencyViolation when deploying the Mesos TOSCA Template: https://github.com/indigo-dc/im/issues/134
* InvalidPermission.Duplicate when opening ports for TOSCA Template: https://github.com/indigo-dc/im/issues/136
* Error saving TOSCA data: https://github.com/indigo-dc/im/issues/135

#### Installation & Configuration

* To upgrade to the last version first you have to install the new version using yum or apt tool:<br>
  ``` # yum update IM```<br>
  ``` # apt install python-im```<br>

* As there is a change in the DB format. Old 1.5.0 data must be updated. Use the script: [db_1_5_0_to_1_5_1.py](https://raw.githubusercontent.com/indigo-dc/im/master/scripts/db_1_5_0_to_1_5_1.py) to update the DB format (if you have installed 1.5.0 version) 
or [db_1_4_to_1_5.py](https://raw.githubusercontent.com/indigo-dc/im/master/scripts/db_1_4_to_1_5.py) (if you have installed 1.4.X version):
  * Install new IM 1.5.1 version.
  * In case that you were using a DATA_FILE to store the IM data (in case of 1.4.X version), define the DATA_DB in the im.cfg file.
  * Execute the script .
    * In case that you were using a DATA_FILE you have to specify it as the first parameter of the script.
    If you were using a DATA_DB to store your data this parameter is not needed.
  * The data will be moved to the new format and old data will be renamed as table inf_list_XXXXXX.

* To update the container the user has to:   
  * Stop the old container:<br>
  ```# sudo docker stop im ```<br>
  * Remove the old container:<br>
  ```# sudo docker rm im ```<br>
  * Pull the new image version:<br>
  ```# sudo docker pull indigodatacloud/im``` <br> 
  * Start the new version:
  ```# sudo docker run -d -p 8899:8899 -p 8800:8800 -e IM_DATA_DB=mysql://username:password@server/db_name --name im indigodatacloud/im  ``` 
  <br>

#### Artefacts
* CentOS7
  * [IM-1.5.1-1.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/IM-1.5.1-1.el7.noarch.rpm)
* Ubuntu14.04
  * [python-im_1.5.1-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-im_1.5.1-1_all.deb)
* Container
  * [indigodatacloud/im:indigo_1](https://hub.docker.com/r/indigodatacloud/im/tags/)


## <a name="nd"></a>Nova-Docker v. 13.0.0

#### What's new
* The new version provides better jsut a repackage for Mitaka CMF

#### Installation & Configuration
* Please follow the instructions provided at the link - https://indigo-dc.gitbooks.io/openstack-nova-docker/content/docs/install.html`<br>
  
#### Artefacts
* CentOS7
  * [python-nova-docker-13.0.4_indigo-1.el7.local.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/python-nova-docker-12.0.4_indigo-1.el7.local.noarch.rpm)
* Ubuntu14.04
  * [nova-compute-docker_13.0.0_indigo-1_all.deb ](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/nova-compute-docker_12.0.0_indigo-1_all.deb )
  * [python-nova-docker_13.0.0_indigo-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-nova-docker_12.0.0_indigo-1_all.deb)


## <a name="roc"></a>rOCCI-cli v. 3.4.9

#### What's new
This is a maintenance release for the 4.3.x series. It introduces, among others:
* Added support for actions returning mixin(s)
* Added support for resizing via partial updates, e.g. ``` `--action update --resource /compute/XYZ --mixin resource_tpl#small` ```

#### List of RfCs
* support for actions returning mixins
* support for resizing via partial updates

#### Installation & Configuration
* Details are available at [rOCCI on GitBOOK](https://www.gitbook.com/book/indigo-dc/rocci/details)

#### Artefacts
* CentOS7
  * [occi-cli-4.3.9+20170214132548-1.el7.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/occi-cli-4.3.9+20170214132548-1.el7.x86_64.rpm)
* Ubuntu14.04
  * [occi-cli_4.3.9+20170214125535-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/occi-cli_4.3.9+20170214125535-1_amd64.deb)

