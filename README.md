# insights-inventory-exporter
Script to export inventory from cloud.redhat.com


# Help
~~~
#./insights-inventory-exporter.py -h
Usage: insights-inventory-exporter.py [options]

Options:
  -h, --help            show this help message and exit
  -l LOGIN, --login=LOGIN
                        Login user
  -f FILENAME, --filename=FILENAME
                        Login user
  -p PASSWORD, --password=PASSWORD
                        Password for specified user. Will prompt if omitted
  -s SERVER, --server=SERVER
                        FQDN of server - omit https://
  -v, --verbose         Verbose output
  -d, --debug           Debugging output (debug output enables verbose)
~~~


# Example output
~~~
$ cat compact_version-rhn-support-wpinheir.csv 
id,server,reporter,arch,core_per_sockets,infrastructure.type,number_of_cpus,number_of_socket,satellite_managed,subscription_status,satellite_id,hypervisor
4e42190e-de97-4f7b-a119-e0efcc40589a,vm001.local.domain,puptoo,x86_64,1,virtual,8,8,False,no subscription status key,,No hypervisor
4914e435-d49e-4f7f-8fac-73614141824c,vm007.local.domain,puptoo,x86_64,1,virtual,8,8,False,no subscription status key,,No hypervisor
a99297d7-3bf8-47e4-8547-83ee97f886e1,vm0005.local.domain,yupana,x86_64,1,virtual,8,8,True,Fully entitled,944e253d-09a8-444b-acc0-7bb1203a1b57,No hypervisor
~~~

Also the file `cloud.redhat.com_output-<account_login>.json` will be created when using the flag `-d`. Note, in this file you will be able to see the `partial` information of your Content Host.

# How to implement this script
- Clone the project
~~~
# git@github.com:sideangleside/insights-inventory-exporter.git
# cd insights-inventory-exporter
~~~
- Create a new virtual environment using python 2.7
~~~
# python2.7 -m virtualenv /tmp/.virtualenv/insights-inventory-exporter
~~~
- Load it
~~~
$ source /tmp/.virtualenv/insights-inventory-exporter/bin/activate
(insights-inventory-exporter) $
~~~
- Install the requirements
~~~
(insights-inventory-exporter) $ pip install -r requirements 
~~~
- Uset it.
~~~
./insights-inventory-exporter.py
~~~