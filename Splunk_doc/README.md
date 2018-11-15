# Local user configuraion change to monitor directory, load file and extract fields from vmstat output using regular expression in [Splunk](https://www.splunk.com/) on Windows Server
## Splunk CLI and update config steps
 * ### File load
 Using below command you can load file one at a time:
```
.\splunk.exe add oneshot "C:\Path\to\log\file.txt" -sourcetype vmstat_monitor
```

 * ###	Directory monitoring
Then you can add monitor the directory using CLI:
```
.\splunk.exe add monitor C:\Path\to\log\
```
Or can be added below entries in $SPLUNK_HOME\etc\apps\search\local\\[inputs.conf](http://docs.splunk.com/Documentation/Splunk/7.2.0/Admin/Inputsconf) config file setting to monitor the directory:
```
[monitor://C:\Path\to\log\]
disabled = false
```
 * ###	Source Type configuration
For example, below vmstat output stored in a file called C:\Path\to\log\file.txt and you want to extract the filed using regular expression in the configuration file.
```
procs -----------memory---------- ---swap-- -----io---- --system-- -----cpu------ ---timestamp---
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 1  0 308096 4078676 2021572 52275020    0    0    72   335    1    1  4  3 92  1  0    2018-11-06 22:10:14 GMT
 0  0 308096 4047248 2021572 52274988    0    0     0     4 2781 9050  3  3 94  0  0    2018-11-06 22:10:15 GMT
 0  0 308096 4034700 2021572 52275532    0    0     0     0 1571 4067  1  1 98  0  0    2018-11-06 22:10:16 GMT
 0  0 308096 4034340 2021572 52275536    0    0     0   832  792 3505  0  0 99  0  0    2018-11-06 22:10:17 GMT
 0  0 308096 4043140 2021572 52275544    0    0     0    84  846 3384  0  0 99  0  0    2018-11-06 22:10:18 GMT
 1  0 308096 4088800 2021572 52275040    0    0     0    88 2356 7276  2  3 95  0  0    2018-11-06 22:10:19 GMT
 0  0 308096 4081724 2021572 52274992    0    0     0     4 2257 7110  1  2 97  0  0    2018-11-06 22:10:20 GMT
 0  0 308096 4092804 2021572 52274044    0    0     0   564 1138 1692  1  1 99  0  0    2018-11-06 22:10:21 GMT
 1  0 308096 4094208 2021572 52273924    0    0     0   136 1197 1542  0  1 99  0  0    2018-11-06 22:10:22 GMT
 0  0 308096 4107812 2021580 52273948    0    0     0   664 1735 2496  1  1 98  0  0    2018-11-06 22:10:23 GMT
 0  0 308096 4118804 2021580 52273920    0    0     0   440  944 1482  0  0 99  0  0    2018-11-06 22:10:24 GMT
 0  0 308096 4119452 2021580 52273884    0    0     0   100  670  776  0  0 100  0  0   2018-11-06 22:10:25 GMT
 0  0 308096 4119700 2021580 52273888    0    0     0     0  551  565  0  0 100  0  0   2018-11-06 22:10:26 GMT
 0  0 308096 4119824 2021580 52273892    0    0     0     0  573  614  0  0 99  0  0    2018-11-06 22:10:27 GMT
 0  0 308096 4119824 2021580 52273896    0    0     0   344  668 1101  0  0 99  0  0    2018-11-06 22:10:28 GMT
 0  0 308096 4119928 2021580 52273900    0    0     0     0  580  556  0  0 100  0  0   2018-11-06 22:10:29 GMT
 0  0 308096 4121052 2021580 52273912    0    0     0    64  667  679  0  0 100  0  0   2018-11-06 22:10:30 GMT
 0  0 308096 4121076 2021580 52273916    0    0     0     0  722  992  0  0 99  0  0    2018-11-06 22:10:31 GMT
```
Go to $SPLUNK_HOME\etc\apps\search\local\ directory and update the below two .conf files. In [props.conf](http://docs.splunk.com/Documentation/Splunk/7.2.0/Admin/Propsconf) file add below entries.
```
[vmstat_monitor]
MAX_TIMESTAMP_LOOKAHEAD = 20
NO_BINARY_CHECK = 1
SHOULD_LINEMERGE = FALSE
pulldown_type = 1
REPORT-myname = vmstat_fields
```
And in [transforms.conf](http://docs.splunk.com/Documentation/Splunk/7.2.0/Admin/Transformsconf) file add below entries.
```
[vmstat_fields]
REGEX = \s+(?<r>[^\s]*)\s+(?<b>[^\s]*)\s+(?<swpd>[^\s]*)\s+(?<free>[^\s]*)\s+(?<buff>[^\s]*)\s+(?<cache>[^\s]*)\s+(?<si>[^\s]*)\s+(?<so>[^\s]*)\s+(?<bi>[^\s]*)\s+(?<bo>[^\s]*)\s+(?<in>[^\s]*)\s+(?<cs>[^\s]*)\s+(?<us>[^\s]*)\s+(?<sy>[^\s]*)\s+(?<id>[^\s]*)\s+(?<wa>[^\s]*)\s+(?<st>[^\s]*)\s+(?<tm>.*)
```
# Global conifguration change to monitor directory, load file and extract fields from comma delimited dstat output file in [Splunk](https://www.splunk.com/) on Windows Server
## Before loading a file first create the source type in [inputs.conf](http://docs.splunk.com/Documentation/Splunk/7.2.0/Admin/Inputsconf).
In $SPLUNK_HOME\etc\system\local\ directory, here we choose system instead app directory because this change will reflect to all the users.
```
[default]
sourcetype = dstat_type

```
## Splunk CLI and update config steps
 * ### File load
 Using below command you can load file one at a time:
```
.\splunk.exe add oneshot "C:\Path\to\log\file.txt" -sourcetype dstat_type
```

 * ###	Directory monitoring
Then you can add monitor the directory using CLI:
```
.\splunk.exe add monitor C:\Path\to\log\ -sourcetype dstat_type
```
Or can be added below entries in $SPLUNK_HOME\etc\system\local\\[inputs.conf](http://docs.splunk.com/Documentation/Splunk/7.2.0/Admin/Inputsconf) config file setting to monitor the directory:
```
[monitor://C:\path\to\dstat_monitor]
sourcetype = dstat_type
disabled = false
```
 * ###	Source Type configuration
For example, below dstat output stored in a file called C:\Path\to\log\file.txt and you want to extract the comma delimited fileds in the configuration file. You can apply multiple types of line format as per below:

Suppose you have dstat_server1.txt, dstat_server2.txt, dstat_server3.txt and dstat_server4.txt files having some colunms having same headings however some columns are different heading then you you can apply the changes in props.conf and transform.conf as per below:

Here below the fore files contais the data:
dstat_server1.txt
```
"system","total cpu usage",,,,,,"memory usage",,,,"net/total",,"/",,"/shm",,"/boot",,"/home",,"/tmp",,"/var",,"/usr",,"/opt",,"/data",,"/Webform",,"/EventRecon",
"date/time","usr","sys","idl","wai","hiq","siq","used","buff","cach","free","recv","send","used","free","used","free","used","free","used","free","used","free","used","free","used","free","used","free","used","free","used","free","used","free"
12-11 07:35:42,0.942,1.912,97.068,0.066,0.000,0.012,1129115648.0,867491840.0,5917843456.0,340217856.0,0.0,0.0,11922944000.0,43035541504.0,0.0,25769803776.0,163545088.0,364879872.0,1703673856.0,410075136.0,501809152.0,4782620672.0,1748340736.0,3536089088.0,4808355840.0,2061414400.0,2799792128.0,7769124864.0,289646379008.0,189126688768.0,224772096.0,17684209664.0,4829757440.0,523849138176.0,
12-11 07:35:43,2.500,4.0,93.500,0.0,0.0,0.0,1129136128.0,867491840.0,5917855744.0,340185088.0,3539.0,2049.0,11922944000.0,43035541504.0,0.0,25769803776.0,163545088.0,364879872.0,1703673856.0,410075136.0,501809152.0,4782620672.0,1748340736.0,3536089088.0,4808355840.0,2061414400.0,2799804416.0,7769112576.0,289646379008.0,189126688768.0,224772096.0,17684209664.0,4829757440.0,523849138176.0,
12-11 07:35:44,1.0,0.500,98.500,0.0,0.0,0.0,1129136128.0,867491840.0,5917855744.0,340185088.0,3192.0,1014.0,11922944000.0,43035541504.0,0.0,25769803776.0,163545088.0,364879872.0,1703673856.0,410075136.0,501809152.0,4782620672.0,1748340736.0,3536089088.0,4808355840.0,2061414400.0,2799804416.0,7769112576.0,289646379008.0,189126688768.0,224772096.0,17684209664.0,4829757440.0,523849138176.0,
12-11 07:35:45,0.505,1.010,98.485,0.0,0.0,0.0,1129136128.0,867495936.0,5917851648.0,340185088.0,2460.0,788.0,11922944000.0,43035541504.0,0.0,25769803776.0,163545088.0,364879872.0,1703673856.0,410075136.0,501809152.0,4782620672.0,1748340736.0,3536089088.0,4808355840.0,2061414400.0,2799804416.0,7769112576.0,289646379008.0,189126688768.0,224772096.0,17684209664.0,4829757440.0,523849138176.0,
12-11 07:35:46,1.0,0.500,98.500,0.0,0.0,0.0,1129132032.0,867495936.0,5917855744.0,340185088.0,2714.0,1014.0,11922944000.0,43035541504.0,0.0,25769803776.0,163545088.0,364879872.0,1703673856.0,410075136.0,501809152.0,4782620672.0,1748340736.0,3536089088.0,4808355840.0,2061414400.0,2799804416.0,7769112576.0,289646379008.0,189126688768.0,224772096.0,17684209664.0,4829757440.0,523849138176.0,
12-11 07:35:47,0.503,0.503,98.995,0.0,0.0,0.0,1129099264.0,867495936.0,5917855744.0,340217856.0,3706.0,788.0,11922944000.0,43035541504.0,0.0,25769803776.0,163545088.0,364879872.0,1703673856.0,410075136.0,501809152.0,4782620672.0,1748340736.0,3536089088.0,4808355840.0,2061414400.0,2799804416.0,7769112576.0,289646379008.0,189126688768.0,224772096.0,17684209664.0,4829757440.0,523849138176.0,
12-11 07:35:48,0.498,0.995,98.010,0.498,0.0,0.0,1129099264.0,867495936.0,5917855744.0,340217856.0,2310.0,1014.0,11922944000.0,43035541504.0,0.0,25769803776.0,163545088.0,364879872.0,1703673856.0,410075136.0,501809152.0,4782620672.0,1748340736.0,3536089088.0,4808355840.0,2061414400.0,2799804416.0,7769112576.0,289646379008.0,189126688768.0,224772096.0,17684209664.0,4829757440.0,523849138176.0,
12-11 07:35:49,1.500,0.500,98.0,0.0,0.0,0.0,1129099264.0,867495936.0,5917855744.0,340217856.0,3858.0,788.0,11922944000.0,43035541504.0,0.0,25769803776.0,163545088.0,364879872.0,1703673856.0,410075136.0,501809152.0,4782620672.0,1748340736.0,3536089088.0,4808355840.0,2061414400.0,2799804416.0,7769112576.0,289646379008.0,189126688768.0,224772096.0,17684209664.0,4829757440.0,523849138176.0,
```
dstat_server2.txt
```
"system","total cpu usage",,,,,,"memory usage",,,,"net/total",
"date/time","usr","sys","idl","wai","hiq","siq","used","buff","cach","free","recv","send"
12-11 07:35:41,3.812,2.907,92.404,0.857,0.000,0.020,7972237312.0,2226438144.0,54714978304.0,2524286976.0,0.0,0.0
12-11 07:35:42,3.750,1.250,95.0,0.0,0.0,0.0,8017121280.0,2226442240.0,54714966016.0,2479411200.0,11425.0,15246.0
12-11 07:35:43,15.763,0.834,83.403,0.0,0.0,0.0,8034279424.0,2226442240.0,54714966016.0,2462253056.0,10984.0,6606.0
12-11 07:35:44,5.583,2.833,91.583,0.0,0.0,0.0,8079622144.0,2226442240.0,54715011072.0,2416865280.0,16828.0,10395.0
12-11 07:35:45,4.170,4.254,91.576,0.0,0.0,0.0,8078053376.0,2226442240.0,54715027456.0,2418417664.0,14744.0,16434.0
12-11 07:35:46,3.503,2.085,94.412,0.0,0.0,0.0,8078774272.0,2226442240.0,54715031552.0,2417692672.0,34424.0,45976.0
12-11 07:35:47,4.925,3.506,91.569,0.0,0.0,0.0,8119271424.0,2226450432.0,54714998784.0,2377220096.0,31377.0,9773.0
12-11 07:35:48,4.333,3.250,92.417,0.0,0.0,0.0,8089038848.0,2226450432.0,54715023360.0,2407428096.0,13033.0,15332.0
```
dstat_server3.txt
```
"system","total cpu usage",,,,,,"memory usage",,,,"net/total",,"/",,"/shm",,"/boot",,"/home",,"/opt",,"/tmp",,"/usr",,"/var",,"/data",
"date/time","usr","sys","idl","wai","hiq","siq","used","buff","cach","free","recv","send","used","free","used","free","used","free","used","free","used","free","used","free","used","free","used","free","used","free"
12-11 07:35:42,0.651,0.529,98.730,0.090,0.000,0.001,3373518848.0,1297600512.0,55549407232.0,7214108672.0,0.0,0.0,18753716224.0,36070551552.0,12288.0,25769791488.0,172601344.0,339046400.0,760840192.0,262463488.0,4311683072.0,6123016192.0,575610880.0,3517702144.0,7178436608.0,1142464512.0,1897689088.0,3319631872.0,355457990656.0,71384637440.0,
12-11 07:35:43,0.0,0.250,99.750,0.0,0.0,0.0,3373260800.0,1297600512.0,55549411328.0,7214362624.0,8911.0,1349.0,18753716224.0,36070551552.0,12288.0,25769791488.0,172601344.0,339046400.0,760840192.0,262463488.0,4311678976.0,6123020288.0,575610880.0,3517702144.0,7178436608.0,1142464512.0,1897689088.0,3319631872.0,355457990656.0,71384637440.0,
12-11 07:35:44,0.0,0.250,99.750,0.0,0.0,0.0,3373187072.0,1297600512.0,55549411328.0,7214436352.0,6944.0,1216.0,18753716224.0,36070551552.0,12288.0,25769791488.0,172601344.0,339046400.0,760840192.0,262463488.0,4311678976.0,6123020288.0,575610880.0,3517702144.0,7178436608.0,1142464512.0,1897689088.0,3319631872.0,355457990656.0,71384637440.0,
12-11 07:35:45,0.083,0.167,99.750,0.0,0.0,0.0,3373051904.0,1297600512.0,55549411328.0,7214571520.0,6086.0,778.0,18753716224.0,36070551552.0,12288.0,25769791488.0,172601344.0,339046400.0,760840192.0,262463488.0,4311678976.0,6123020288.0,575606784.0,3517706240.0,7178436608.0,1142464512.0,1897689088.0,3319631872.0,355457990656.0,71384637440.0,
12-11 07:35:46,0.167,0.667,98.582,0.584,0.0,0.0,3373056000.0,1297600512.0,55549415424.0,7214563328.0,7578.0,778.0,18753716224.0,36070551552.0,12288.0,25769791488.0,172601344.0,339046400.0,760840192.0,262463488.0,4311678976.0,6123020288.0,575614976.0,3517698048.0,7178436608.0,1142464512.0,1897701376.0,3319619584.0,355457990656.0,71384637440.0,
12-11 07:35:47,2.007,1.003,94.314,2.592,0.0,0.084,3373305856.0,1297600512.0,55549427712.0,7214301184.0,7314.0,852.0,18753716224.0,36070551552.0,12288.0,25769791488.0,172601344.0,339046400.0,760840192.0,262463488.0,4311678976.0,6123020288.0,575614976.0,3517698048.0,7178436608.0,1142464512.0,1897701376.0,3319619584.0,355457990656.0,71384637440.0,
12-11 07:35:48,6.946,1.925,90.795,0.335,0.0,0.0,3373801472.0,1297600512.0,55549419520.0,7213813760.0,47652.0,6375.0,18753716224.0,36070551552.0,12288.0,25769791488.0,172601344.0,339046400.0,760840192.0,262463488.0,4311642112.0,6123057152.0,575614976.0,3517698048.0,7178436608.0,1142464512.0,1897701376.0,3319619584.0,355457990656.0,71384637440.0,
12-11 07:35:49,7.191,2.174,90.385,0.167,0.0,0.084,3374608384.0,1297600512.0,55549423616.0,7213002752.0,9625.0,1722.0,18753716224.0,36070551552.0,12288.0,25769791488.0,172601344.0,339046400.0,760840192.0,262463488.0,4311654400.0,6123044864.0,575614976.0,3517698048.0,7178436608.0,1142464512.0,1897701376.0,3319619584.0,355457990656.0,71384637440.0,
```

dstat_server4.txt
```
"system","total cpu usage",,,,,,"memory usage",,,,"net/total",,"/",,"/shm",,"/boot",,"/home",,"/tmp",,"/opt",,"/var",,"/usr",,"/data",
"date/time","usr","sys","idl","wai","hiq","siq","used","buff","cach","free","recv","send","used","free","used","free","used","free","used","free","used","free","used","free","used","free","used","free","used","free"
12-11 07:35:43,0.302,0.291,99.391,0.014,0.000,0.002,4064350208.0,1310138368.0,2025979904.0,60156264448.0,0.0,0.0,16732798976.0,38225686528.0,0.0,25769803776.0,162975744.0,365449216.0,250773504.0,1862975488.0,498425856.0,4786003968.0,3197435904.0,7371481088.0,1448583168.0,3835846656.0,4048474112.0,707506176.0,56325390336.0,315489677312.0,
12-11 07:35:44,0.250,0.125,99.625,0.0,0.0,0.0,4064235520.0,1310138368.0,2025984000.0,60156375040.0,2518.0,468.0,16732798976.0,38225686528.0,0.0,25769803776.0,162975744.0,365449216.0,250773504.0,1862975488.0,498425856.0,4786003968.0,3197435904.0,7371481088.0,1448583168.0,3835846656.0,4048474112.0,707506176.0,56325390336.0,315489677312.0,
12-11 07:35:45,0.375,0.250,99.374,0.0,0.0,0.0,4064362496.0,1310138368.0,2025984000.0,60156248064.0,4524.0,33945.0,16732798976.0,38225686528.0,0.0,25769803776.0,162975744.0,365449216.0,250773504.0,1862975488.0,498425856.0,4786003968.0,3197411328.0,7371505664.0,1448583168.0,3835846656.0,4048474112.0,707506176.0,56325390336.0,315489677312.0,
12-11 07:35:46,0.125,0.250,99.625,0.0,0.0,0.0,4064514048.0,1310138368.0,2025959424.0,60156121088.0,1822.0,170.0,16732798976.0,38225686528.0,0.0,25769803776.0,162975744.0,365449216.0,250773504.0,1862975488.0,498425856.0,4786003968.0,3197411328.0,7371505664.0,1448583168.0,3835846656.0,4048474112.0,707506176.0,56325390336.0,315489677312.0,
12-11 07:35:47,0.250,0.125,99.625,0.0,0.0,0.0,4064514048.0,1310138368.0,2025959424.0,60156121088.0,3142.0,170.0,16732798976.0,38225686528.0,0.0,25769803776.0,162975744.0,365449216.0,250773504.0,1862975488.0,498425856.0,4786003968.0,3197411328.0,7371505664.0,1448583168.0,3835846656.0,4048474112.0,707506176.0,56325390336.0,315489677312.0,
12-11 07:35:48,0.250,0.250,99.501,0.0,0.0,0.0,4064514048.0,1310138368.0,2025959424.0,60156121088.0,1676.0,410.0,16732798976.0,38225686528.0,0.0,25769803776.0,162975744.0,365449216.0,250773504.0,1862975488.0,498425856.0,4786003968.0,3197411328.0,7371505664.0,1448583168.0,3835846656.0,4048474112.0,707506176.0,56325390336.0,315489677312.0,
12-11 07:35:49,0.250,0.250,99.375,0.125,0.0,0.0,4064514048.0,1310146560.0,2025959424.0,60156112896.0,3294.0,244.0,16732798976.0,38225686528.0,0.0,25769803776.0,162975744.0,365449216.0,250773504.0,1862975488.0,498425856.0,4786003968.0,3197411328.0,7371505664.0,1448583168.0,3835846656.0,4048474112.0,707506176.0,56325390336.0,315489677312.0,
12-11 07:35:50,0.250,0.250,99.500,0.0,0.0,0.0,4064514048.0,1310146560.0,2025959424.0,60156112896.0,1354.0,170.0,16732798976.0,38225686528.0,0.0,25769803776.0,162975744.0,365449216.0,250773504.0,1862975488.0,498425856.0,4786003968.0,3197411328.0,7371505664.0,1448583168.0,3835846656.0,4048474112.0,707506176.0,56325390336.0,315489677312.0,
```
Then add the below entries in the props.conf file.
```
[dstat_type]
SHOULD_LINEMERGE = False
pulldown_type = 1
REPORT-getfields = dstat_server1, dstat_server2, dstat_server3, dstat_server4
```
And add the transfor rules to transforms.conf to extract fields.
```
[dstat_server1]
DELIMS=","
FIELDS = "system_date_time","usr","sys","idl","wai","hiq","siq","mem_used","mem_buff","mem_cach","mem_free","net_recv","net_send","root_used","root_free","shm_used","shm_free","boot_used","boot_free","home_used","home_free","tmp_used","tmp_free","var_used","var_free","usr_used","usr_free","opt_used","opt_free","data_used","data_free","Webform_used","Webform_free","EventRecon_used","EventRecon_free",

[dstat_server2]
DELIMS=","
FIELDS = "system_date_time","usr","sys","idl","wai","hiq","siq","mem_used","mem_buff","mem_cach","mem_free","net_recv","net_send"

[dstat_server3]
DELIMS=","
FIELDS = "system_date_time","usr","sys","idl","wai","hiq","siq","mem_used","mem_buff","mem_cach","mem_free","net_recv","net_send","root_used","root_free","shm_used","shm_free","boot_used","boot_free","home_used","home_free","opt_used","opt_free","tmp_used","tmp_free","usr_used","usr_free","var_used","var_free","data_used","data_free",

[dstat_server4]
DELIMS=","
FIELDS = "system_date_time","usr","sys","idl","wai","hiq","siq","mem_used","mem_buff","mem_cach","mem_free","net_recv","net_send","root_used","root_free","shm_used","shm_free","boot_used","boot_free","home_used","home_free","tmp_used","tmp_free","opt_used","opt_free","var_used","var_free","usr_used","usr_free","data_used","data_free",
```
Once the change done use the below command in splunk search window to get the .conf change reflect.
```
| extract reload=T
```
# Use an HTML file in a dashboard panel
## Steps
### 1. Put the HTML file in the following directory.
```
$SPLUNK_HOME/etc/apps/<appname>/appserver/static
```
### 2. In the <html> panel, use this syntax to indicate a file from the current app context.
```
<html src="<file_name>.html">
</html>
```
If you are specifying an HTML file from another app context, use this syntax.
```
<html src="<other_app_name>:<file_name>.html">
</html>
```
# Use an image file in a dashboard panel
## Steps

### 1. Put the image file in the following directory.
```
$SPLUNK_HOME/etc/apps/<appname>/appserver/static/images
```
If an /images directory does not already exist, create one and put the file in it.

### 2. Verify that the image file path is accessible by testing the following URL.
```
http://<host>:<port>/static/app/<app_name>/images/<image>
```
For example, use this URL to verify that the my_image.png file is accessible.
```
http://localhost:8001/static/app/search/images/my_image.png
```
### 3. In the <html> panel, use this syntax to indicate a file from the current app context.
```
 <html>
<img src="/static/app/search/images/my_image.png">
</img>
</html>
```
*Note:There are no child options for the <html> element.*

### Example
```
<dashboard>
  <label>test_db</label>
  <row>
    <panel>
      <html>
<!-- Use an image from the current app's /static/images directory -->
        <img src="/static/app/search/images/my_image.png"></img>
      </html>
    </panel>
    <panel>
<!-- Use an HTML file from the webhook app. -->
      <html src="alert_webhook:my_html_file.html">
      </html>
<!--Use an image from the webhook app static/images directory -->
      <html>
        <img src="/static/app/alert_webhook/images/my_other_image.png"></img>
      </html>
    </panel>
  </row>
</dashboard>
```
