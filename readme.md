# SUPER LIGHT HTTP SERVER WITH SERVER SIDE SCRIPT (sq script)
## designed for embedded or small device which run Linux.


* Dependencies: 
  * https://github.com/comarius/mcosocks
  * https://github.com/comarius/mcoutils

### sq script page sample

```javascript
cookie("somecook","somvalue",1);

echo ("<HTML>");
echo ("PAGE GENERATED FROM SQ PLUGIN");

local  conparam="<pre>";

conparam+="</fieldset><fieldset><h2>_request[] table </h2> </br>";
foreach(key,val in _request)
	conparam+="<div >" + key + "=" + val + "</div>\n";

conparam+="</fieldset><fieldset><h2>_get[] table </h2> </br>";
foreach(key,val in _get)
	conparam+="<div >" + key + "=" + val + "</div>\n";

conparam+="</fieldset><fieldset><h2>_context[] table </h2> </br>";
echo ("");
foreach(key,val in _context)
	conparam+="<div >" + key + "=" + val + "</div>\n";

conparam+="</fieldset><fieldset><h2>_post[] table </h2> </br>";

foreach(key,val in _post)
	conparam+="<div >" + key + "=" + val + "</div>\n";


foreach(key,val in _put)
{
	conparam+="<div >" + key + "=" + val + "</div>\n";
}


if("FILENAME" in _post)
{
    conparam+="/var/www/rules-565-221/";
    conparam+="<font color='red'> file size is: " + _post["FILESIZE"]+"</font><br>";

    _this.save_file("/var/www/rules-565-221/upload.txt");
}

conparam+="</fieldset><fieldset><h2>_cookies[] table </h2> </br>";
echo ("");
foreach(key,val in _cookies)
	conparam+="<div >" + key + "=" + val + "</div>\n";

conparam+="</pre>";



echo (conparam);

echo ("all other functions and language support as in <a href='http://www.squirrel-lang.org/'>squirrel-lang</a>");

echo ("</HTML>");

````

### TEST

```javascript

Server Software:        
Server Hostname:        localhost
Server Port:            8000

Document Path:          /
Document Length:        1750 bytes

Concurrency Level:      128
Time taken for tests:   2.638 seconds
Complete requests:      10000
Failed requests:        7
   (Connect: 0, Receive: 0, Length: 7, Exceptions: 0)
Write errors:           0
Total transferred:      19861824 bytes
HTML transferred:       17521824 bytes
<b>Requests per second:    3791.09 [#/sec] (mean)</b>
Time per request:       33.763 [ms] (mean)
Time per request:       0.264 [ms] (mean, across all concurrent requests)
Transfer rate:          7353.31 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.3      0       5
Processing:     2    9   8.8      9     647
Waiting:        1    9   8.8      9     647
Total:          5    9   8.8      9     647

Percentage of the requests served within a certain time (ms)
  50%      9
  66%      9
  75%      9
  80%      9
  90%     10
  95%     10
  98%     10
  99%     11
 100%    647 (longest request)



Benchmarking localhost (be patient)
...
Completed 10000 requests
Finished 10000 requests


Server Software:        
Server Hostname:        localhost
Server Port:            8000

Document Path:          /some_images.html
Document Length:        543 bytes

Concurrency Level:      128
Time taken for tests:   2.718 seconds
Complete requests:      10000
Failed requests:        0
Write errors:           0
Total transferred:      7760000 bytes
HTML transferred:       5430000 bytes
<b>Requests per second:    3679.64 [#/sec] (mean)</b>
Time per request:       34.786 [ms] (mean)
Time per request:       0.272 [ms] (mean, across all concurrent requests)
Transfer rate:          2788.48 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.2      0       4
Processing:     6    9   9.1      9     467
Waiting:        6    9   9.1      9     467
Total:          7    9   9.2      9     470

Percentage of the requests served within a certain time (ms)
  50%      9
  66%      9
  75%      9
  80%      9
  90%     10
  95%     10
  98%     11
  99%     12
 100%    470 (longest request)




Benchmarking localhost (be patient)
Completed 1000 requests
...
Completed 10000 requests
Finished 10000 requests


Server Software:        mariux/1.0
Server Hostname:        localhost
Server Port:            8000

Document Path:          /somescript.sqs?param=value
Document Length:        1210 bytes

Concurrency Level:      128
Time taken for tests:   3.954 seconds
Complete requests:      10000
Failed requests:        4766
   (Connect: 0, Receive: 0, Length: 4766, Exceptions: 0)
Write errors:           0
Non-2xx responses:      4766
Total transferred:      13010716 bytes
HTML transferred:       9483466 bytes
<b>Requests per second:    2529.36 [#/sec] (mean)</b>
Time per request:       50.606 [ms] (mean)
Time per request:       0.395 [ms] (mean, across all concurrent requests)
Transfer rate:          3213.75 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0   24 266.9      0    3015
Processing:     4   17  39.8     12     680
Waiting:        4   15  39.7     11     679
Total:          5   41 297.9     12    3695

Percentage of the requests served within a certain time (ms)
  50%     12
  66%     13
  75%     14
  80%     15
  90%     21
  95%     24
  98%     68
  99%    142
 100%   3695 (longest request)


<H1>System info for benchmarking</H1>
processor	: 0,1,2,3,4...8
vendor_id	: GenuineIntel
cpu family	: 6
model		: 30
model name	: Intel(R) Core(TM) i7 CPU       Q 740  @ 1.73GHz
stepping	: 5
cpu MHz		: 933.000
cache size	: 6144 KB
<!---->



###  You can check my reverse ssh online service and online key value database at 

[reverse ssh as a service](http://www.mylinuz.com)

[key value database as a service](https://www.meeiot.org)

