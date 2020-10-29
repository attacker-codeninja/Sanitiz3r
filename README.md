# Sanitiz3r
Sanitiz3r is a lightweight tool designed to filter based on a set of defined rules and determine the validity of subdomains of a website discovered through bunch of recon tools for enumerating subdomains. Sanitiz3r takes in words that could be the domains of the website (such as domain.com, domain.net, domain.xyz, etc) as well as list(s) of subdomains that you have discovered during recon or similar activity.

The tool, after being provided with necessary inputs generates an output of filtered subdomain(s) based on the defined rules (such as the domains of the website their corresponding TLD)


Sanitiz3r works offline by default but can optionally passed with `-a / --active` flag so it gets the validity of the filtered list of subdomains. Thereby returning the `HTTP Status` and `title` of each subdomains in the report.

The output is given in HTML and .txt format. The later contains same subdomains without the `HTTP/HTTPS` prefix.

# Screenshots

<img width="681" alt="sanitiz3r" src="https://user-images.githubusercontent.com/32202226/37572950-cf78c26e-2b12-11e8-804f-0c4c5ff0ce55.png">


# Installation

Sanitiz3r supports only **Python 3**.

```
$ git clone https://github.com/sawzeeyy/Sanitiz3r.git
$ cd Sanitiz3r
$ pip3 install -r requirements.txt
```
**Additional for Linux users**
```
$ ln -s /FULL_PATH/sanitiz3r.py /usr/local/bin/Sanitiz3r
```
Example:
```
ln -s /Users/Sawzeeyy/Desktop/Sanitiz3r/sanitiz3r.py /usr/local/bin/Sanitiz3r
```
Then you can run Sanitiz3r directly using
```
$ Sanitiz3r
```

# Dependencies

Sanitiz3r depends on the os, sys, argparse, re, requests, http.client, and the webbrowser python modules. These dependencies can all be installed using [pip](https://pypi.python.org/pypi/pip).

**Python 3:** `$ pip3 install -r requirements.txt`

**For Coloring on Windows:** `pip install win_unicode_console colorama`

# Usage

| Short Form        | Long Form           | Description  |
| ------------- |-------------| -----|
| -v | --verbose | Optionally log all information about the current process |
| -a | --active | Optionally choose to take Sanitiz3r online to detemine the validity of subdomains |
| -d | --domain | Specify the domain name(s) or a text file containing the domains |
| -i | --input | Specify the input file(s) containing the subdomaains |
| -o | --output| Optionally specify the filename to save the report. Default: *domain_sanitizer.html* |
| -t | --thread | Specify the number of threads, default=10 |
| | --timeout | Specify the maximum time to request for a URL, default=10 |
| -r | --resolved | Optionally filter resolved URLs |

# Examples
- To list all the basic options and switches use -h switch:

`python3 sanitiz3r.py -h`

- To filter the contents of an input file against a particular domain and generate output:

`python3 sanitiz3r.py -d domain.com -i file1.txt`

- To specify the hosts / domains file:

`python3 sanitiz3r.py -v -a -d domains.txt -i file1.txt,file2.txt -o customname.html`

- To specify the filename of the generated output:

`python3 sanitiz3r.py -d domain.com -i file1.txt -o customname.html`

- To filter and determine the status of subdomains:

`python3 sanitiz3r.py -a -d domain.com -i file1.txt`

- To view realtime information about the current process.:

`python3 sanitiz3r.py -v -a -d domain.com -i file1.txt`

- To use all the features of sanitiz3r at once:

`python3 sanitiz3r.py -v -a -d domain.com,domain2.net -i file1.txt,file2.txt -o customname.html`


# License

Sanitiz3r is licensed under the GNU GPL license. take a look at the [LICENSE](/LICENSE) for more information.

# Contribution

Bug reports and pull requests are welcome on GitHub at https://github.com/sawzeeyy/sanitiz3r.

# Thanks

Special thanks to [Yusuf Yazir](https://twitter.com/hacklad "Yusuf Yazir, @hacklad on Twitter") for his great contributions that helped in improving the tool.

# Changelog

[CHANGELOG](/CHANGELOG)
