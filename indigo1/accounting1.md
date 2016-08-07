# Accounting v. 1.0.0-1

Summary:
* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [Documentation](#id6)
  * [List of Artifacts](#id7)


## Release Notes

### What's new


#### List of RfCs 


### Deployment Notes

* Installation methods: 
  * Installation not required as everything is in the Docker container
* Set up from source: 
  * See [https://github.com/indigo-dc/Accounting/blob/master/README.md](https://github.com/indigo-dc/Accounting/blob/master/README.md)
* Running from Docker:
  * Get the script 

    ```wget https://github.com/indigo-dc/Accounting/blob/master/docker/run_container.sh```

  * Configure **MYSQL_ROOT_PASSWROD** (and APEL user password) in *run_container.sh*
  * Configure **ALLOWED FOR GET**, **SERVER_IAM_ID**, **SERVER_IAM_SECRET**, **DJANGO_SECRET_KEY** in *run_container.sh*, and afterwards run:

    ```chmod a+x run_container.sh
    ./run_container.sh```



### Known Issues


### Documentation


### List of Artifacts

Docker Container:
* [indigodatacloud/accounting:indigo_1](https://hub.docker.com/r/indigodatacloud/accounting/)

