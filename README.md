# Virtual host scanner
This is a basic HTTP scanner that'll enumerate virtual hosts on a given IP address. During recon, this might help expand the target by detecting old or deprecated code. It may also reveal hidden hosts that are statically mapped in the developer's `/etc/hosts` file.

## Usage
The tool comes with a few basic options. They are listed below and help narrow down virtual hosts.

```
ruby scan.rb --ip=192.168.1.101 --host=domain.tld
```

Here's a list of all available options:

 - **--ignore-http-codes**: a comma-separated list of HTTP status codes to be ignored in the scan results. This may become useful when the scan results are poluted with false-positives that are identified by their HTTP response code.
 - **--ignore-content-length**: a content length filter which should be ignored in the scan results. This may become useful when a server returns a static page on every virtual host guess.
 - **--port**: when the web server isn't running on port 80.
 - **--wordlist**: specify an alternative location for the wordlist.
 - **--ssl**: `on` or `off` depending on whether you want to connect with SSL.
 - **--output**: optionally specify an alternative file to write the output to. Defaults to `output.txt` in the current directory.

## Wordlist
There's a default, small, wordlist in this repository. To use your own wordlist, use the **--wordlist** option. **%s** will be replaced with the given **--host** header in every line of the wordlist file.

# vhost-brute
A PHP tool to brute force vhost configured on a server.  

```
Usage: php vhost-brute.php [OPTIONS]

Options:
	--domain	set domain
	--fail		max fail (http code=0) before exiting, default=-1, unlimited
	-h, --help	print this help
	--ip		set server ip address
	--port		set port
	--ssl		force ssl
	--threads	set maximum threads, default=1
	--wordlist	set plain text file that contains subdomains to test

Examples:
	php vhost-brute.php --ip=xxx.xxx.xxx.xxx --domain=example.com --wordlist=sub.txt --threads=5
```

<img src="https://raw.githubusercontent.com/gwen001/vhost-brute/master/example.jpg" alt="Virtual Host Brute Force example">
<br><br>

I don't believe in license.  
You can do want you want with this program.  