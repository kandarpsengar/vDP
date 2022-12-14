
<h1>Steps to Install vDP on AWS EC2 Instance</h1>
<h2>Software Links:</h2>

<ul>
  <li>DataPower Gateway for Linux : https://www.ibm.com/docs/en/datapower-gateway/10.5?topic=virtual-datapower-gateway-linux</li>
  <li>Software link (IBM): https://w3east-limited-use.cpc.ibm.com/isc/esd/dswdown/home?ticket=Xa.2%2FXb.ddeX-Pn5_UKDYD1[…]2FXi.%2FXY.knac%2FXZ.w2pFXrBgEeGsT61hXmhfBTTs6sUFhFAF</li>
<li>Minimum System Requirements:	https://www.ibm.com/software/reports/compatibility/clarity-reports/report/html/softwareReqsForProduct?deliverableId=427BEAC0EDBA11ECBEE19EDF136D6557&osPlatforms=Linux&duComponentIds=S006|S007|S004|S005|S003|S002|S001|C010|C009|C008&mandatoryCapIds=16&optionalCapIds=30|341|126|9|1|35|121|20|42|184|185|32|16|33|27|69|124|15|223|26 </li>
  <li>Software (Customer): Passport Advantage</li>
</ul>
<h2>Prerequisites: </h2>


<ul>
  <li>Make sure the version of Linux RHEL is compatible with DataPower</li>
  <li>Install Telnet if you can using command</li>
   <ul>
	   <code>sudo yum install telnet</code>
    </ul>
  <li>Install Python 3</li>
  <ul>
	  <code>wget https://www.python.org/ftp/python/3.10.5/Python-3.10.5.tgz</code>
	  <code>tar xzf Python-3.10.5.tgz</code>
    </ul>
</ul>
<h2>Steps: </h2>
<ul>
<li>	Login to EC2 Instance</li>
<li>	Make sure the pre-requisite is met as per the system requirements.</li>
<li>Download the DataPower Software from the above link </li>
<li>Copy the certificate files certreport39.zip and KeywithIDCredReport.zip (These are the in the box folder, mailto: kandarp.sengar@ibm.com or patrick.bennett@ibm.com )</li>
<li>Install the Data Power by running the below command.</li>
	
<code>sudo yum install idg_lx10502.lts.nonprod.image.x86_64.rpm idg_lx10502.lts.common.x86_64.rpm </code>
	
<li>	Output from the above.</li>
	
<em> Updating Subscription Management repositories.
Unable to read consumer identity

This system is not registered with an entitlement server. You can use subscription-manager to register.

Last metadata expiration check: 1:47:04 ago on Tue 11 Oct 2022 06:18:50 PM UTC.

Dependencies resolved.

===================================================================================

 Package                 Arch   Version           Repository                  Size
 
===================================================================================
Installing:

 ibm-datapower-agoradco-nonpd-image  x86_64 10.5.0.2.345566-1 @commandline               3.1 G
                         
 ibm-datapower-common    x86_64 10.5.0.2.345566-1 @commandline               660 k
 
Installing dependencies:

 boost-filesystem        x86_64 1.66.0-10.el8     rhel-8-appstream-rhui-rpms  49 k
 
 ipvsadm                 x86_64 1.31-1.el8        rhel-8-appstream-rhui-rpms  59 k
 
 schroot                 x86_64 1.6.10-10.el8     epel                       899 k
 

Transaction Summary

===================================================================================

Install  5 Packages

Total size: 3.1 G

Total download size: 1.0 M

Installed size: 3.1 G

Is this ok [y/N]: y

Downloading Packages:

(1/3): ipvsadm-1.31-1.el8.x86_64.rpm               1.9 MB/s |  59 kB     00:00   

(2/3): boost-filesystem-1.66.0-10.el8.x86_64.rpm   1.5 MB/s |  49 kB     00:00  

(3/3): schroot-1.6.10-10.el8.x86_64.rpm            2.8 MB/s | 899 kB     00:00   

-----------------------------------------------------------------------------------

Total                                              2.4 MB/s | 1.0 MB     00:00   

Running transaction check

Transaction check succeeded.

Running transaction test

Transaction test succeeded.

Running transaction

  Preparing        :                                                           1/1 
  
  Installing       : ibm-datapower-agoradco-nonpd-image-10.5.0.2.345566-1.x8   1/5 
  
  Installing       : boost-filesystem-1.66.0-10.el8.x86_64                     2/5 
  
  Running scriptlet: boost-filesystem-1.66.0-10.el8.x86_64                     2/5 
  
  Installing       : schroot-1.6.10-10.el8.x86_64                              3/5 
  
  Installing       : ipvsadm-1.31-1.el8.x86_64                                 4/5 
  
  Running scriptlet: ipvsadm-1.31-1.el8.x86_64                                 4/5 
  
  Running scriptlet: ibm-datapower-common-10.5.0.2.345566-1.x86_64             5/5 
  
  Installing       : ibm-datapower-common-10.5.0.2.345566-1.x86_64             5/5 
  
  Running scriptlet: ibm-datapower-common-10.5.0.2.345566-1.x86_64             5/5 
  
Created symlink /etc/systemd/system/multi-user.target.wants/datapower.service → /usr/lib/systemd/system/datapower.service.


  Verifying        : schroot-1.6.10-10.el8.x86_64                              1/5 
  
  Verifying        : ipvsadm-1.31-1.el8.x86_64                                 2/5 
  
  Verifying        : boost-filesystem-1.66.0-10.el8.x86_64                     3/5 
  
  Verifying        : ibm-datapower-agoradco-nonpd-image-10.5.0.2.345566-1.x8   4/5 
  
  Verifying        : ibm-datapower-common-10.5.0.2.345566-1.x86_64             5/5 
  
Installed products updated.


Installed:

  boost-filesystem-1.66.0-10.el8.x86_64                         
  
  ibm-datapower-agoradco-nonpd-image-10.5.0.2.345566-1.x86_64              
  
  ibm-datapower-common-10.5.0.2.345566-1.x86_64                
  
  ipvsadm-1.31-1.el8.x86_64                                    
  
  schroot-1.6.10-10.el8.x86_64                                  
  

Complete! </em>


<li>	Start DataPower</li>

  </li>
  <ul>
      <code>systemctl start datapower </code>
  </ul>
  </li>
  
  <li>Use one of the three commands login to datapower</li>

  </li>
  <ul>
      <li>telnet 127.0.0.1 2200</li>
      <li>nc 127.0.0.1 2200</li>
      <li>bash -c "cat < /dev/tcp/127.0.0.1/2200"</li>
 </ul>
  <li>	Login as admin/admin and will prompt you to change your password,(Changing your password is required)</li>   
        
  <li>Run below command to configure.</li>
        <ul>
      <code>idg# co</code>
      <li>Global mode</li>
      <li>idg(config)# web-mgmt 0 9090 9090</li>
        </ul>

<li>Output</li> 
        <ul>
      <li>Web management: successfully started</li>
        </ul>
<li>idg(config)# write memory</li> 

<li>Output</li> 
         <ul>
      <li>Overwrite previously saved configuration? Yes/No [y/n]: y</li>
        <li>Configuration saved successfully.</li>
        </ul>
        
 <li>Exit</li> 
         <ul>
      <li>idg(config)# exit</li>
        <li>Overwrite previously saved configuration? Yes/No [y/n]: y</li>
        <li>Configuration saved successfully.</li>
        </ul>

 <li>Login to web-ui using the updated password</li>
 <li>Search for “XML management interface” and enable with all defaults.</li>
 <li>Search for “REST” and enable with all defaults.</li>
        
<h2>Domain Import Shell Script to create the domain if it doesn't exist</h2>

        

#!/bin/bash
        
SOMA_USER=<user>
        
SOMA_PSW=<password>
        
#SOMA URL will be local address or remote EC2
        
SOMA_URL=https://127.0.0.1:5550 
        
OVERWRITE_FILES=false
        
OVERWRITE_OBJECTS=false
        

#Change the astrix (*) to EC2 instance location where folder resides, if you want to connect to #git webhook
        
for dir in */; do        
    # create domain if it doesn't exist        
    for file in "$dir"*; do        
        # if key/cert, upload file        
                 # possibly split shared certs for either upload type or "default" domain        
                 # create key/cert object        
	if [[ "${file: -4}" == ".zip" ]] ; then        
		FILE_B64=$(base64 $file)        
SOMA_REQ=$(cat <<EOF        
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:dp="http://www.datapower.com/schemas/management">        
   <soapenv:Header/>        
   <soapenv:Body>        
      <dp:request domain="${dir:0:-1}">        
         <dp:do-import source-type="ZIP" overwrite-files="$OVERWRITE_FILES" overwrite-objects="$OVERWRITE_OBJECTS">        
            <dp:input-file>$FILE_B64</dp:input-file>        
         </dp:do-import>        
      </dp:request>        
   </soapenv:Body>        
</soapenv:Envelope>
        
EOF
        
)
        
echo $SOMA_REQ > /tmp/1.req
        
curl -k -u $SOMA_USER:$SOMA_PSW --request POST $SOMA_URL -d @/tmp/1.req
        
fi	
      done
        
done	

<h2>Appendix</h2>

  <li>Commands</li> 
         <ul>
      <li>Get all domains </li>
      
         curl -k -u admin:adminadmin --request GET https://127.0.0.1:5554/mgmt/domains/config/
	 
</ul>

  <li>Creating a domain</li> 
         
            
         curl -k -u admin:adminadmin --request PUT https://127.0.0.1:5554/mgmt/config/default/Domain/test -H "Content-Type: application/json" -d '{  "Domain": {    "name": "test",    "mAdminState": "enabled"  }}'
	 

<li>Import the domain </li> 
	 
	 FILE_B64=$(base64 genericexport10112022.zip)
	 SOMA_REQ=$(cat <<EOF
	 <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:dp="http://www.datapower.com/schemas/management">
   	 <soapenv:Header/>
   	 <soapenv:Body>
         <dp:request domain="Generic">
         <dp:do-import source-type="ZIP" overwrite-files="true" overwrite-objects="true">
         <dp:input-file>$FILE_B64</dp:input-file>
         </dp:do-import>
         </dp:request>
         </soapenv:Body>
         </soapenv:Envelope>
         EOF
         )

echo $SOMA_REQ > /tmp/1.req

curl -k -u $SOMA_USER:$SOMA_PSW --request POST $SOMA_URL -d @/tmp/1.req

<li>Upload the key/cert as a file  </li> 

	FILE_B64_CRYPTO=$(base64 webgui-sscert.pem)
	SOMA_REQ_CRYPTO=$(cat <<EOF
	<soapenv:Envelope 
	xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
        xmlns:dp="http://www.datapower.com/schemas/management">
        <soapenv:Header/>
        <soapenv:Body>
        <dp:request domain="default">
        <dp:set-file name="cert:///webgui-sscert.pem">$FILE_B64_CRYPTO</dp:set-file> 
        </dp:request>
        </soapenv:Body>
        </soapenv:Envelope>
        EOF
        )
echo $SOMA_REQ_CRYPTO > /tmp/2.req
	      
curl -k -u $SOMA_USER:$SOMA_PSW --request POST $SOMA_URL -d @/tmp/2.req

	 

     

       
        
  
 
  
  

  
