# Common Options

option | description
--------|-------------
`-#, --progress-bar` | Make curl display a simple progress bar instead of the more informational standard meter.
`-b, --cookie <name=data>` | Supply cookie with request. If no =, then specifies the cookie file to use (see -c).
`-c, --cookie-jar <file name>` | File to save response cookies to.
`-d, --data <data>` | Send specified data in POST request. Details provided below.
`-f, --fail` | Fail silently (don't output HTML error form if returned).
`-F, --form <name=content>` | Submit form data.
`-H, --header <header>` | Headers to supply with request.
`-i, --include` | Include HTTP headers in the output.
`-I, --head` | Fetch headers only.
`-k, --insecure` | Allow insecure connections to succeed.
`-L, --location` | Follow redirects.
`-o, --output <file>` | Write output to . Can use --create-dirs in conjunction with this to create any directories specified in the -o path.
`-O, --remote-name` | Write output to file named like the remote file (only writes to current directory).
`-s, --silent` | Silent (quiet) mode. Use with -S to force it to show errors.
`-v, --verbose` | Provide more information (useful for debugging).
`-w, --write-out <format>` | Make curl display information on stdout after a completed transfer. See man page for more details on available variables. Convenient way to force curl to append a newline to output: -w "\n" (can add to ~/.curlrc).
`-X, --request` | The request method to use.


# GET

### with Authorization header
```
$ curl -H "Content-Type: application/json" \
    -H "Authorization: Bearer xxxx" \
    -X GET http://example.com/data
```

# POST

### with JSON data

```
$ curl -X POST \
    -H "Content-Type: application/json" \
    -d '{"username":"xyz","password":"xyz"}' \
    http://example.com/api/login
```

# PUT

```
$ curl -X PUT \
    -H 'Content-Type: application/json' \
    -d '{"firstName":"Kris", "lastName":"Jordan"}' \
    http://example.com
```

# Examples

### with Authorization header
```
$ curl -i \
    -H 'Accept: application/json' \
    -H 'Authorization: Basic username:password' \
    http://example.com
```

### Download a File
```
// Save as yourfile.tar.gz
$ curl -O http://yourdomain.com/yourfile.tar.gz

// Save as newfile.tar.gz
$ curl -o newfile.tar.gz http://yourdomain.com/yourfile.tar.gz
```

### Download Multiple Files
```
$ curl -O http://yoursite.com/info.html -O http://mysite.com/about.html
```

### Download Files from an FTP Server with or without Authentication
```
$ curl -u username:password -O ftp://yourftpserver/yourfile.tar.gz
```

### Upload Files to an FTP server with or without Authentication
```
$ curl -u username:password -T mylocalfile.tar.gz ftp://yourftpserver
```

### Timing Details With cURL
```
$ curl -w "@curl-format.txt" -o /dev/null -s "http://example.com/"
```

## References
- https://gist.github.com/subfuzion/08c5d85437d5d4f00e58
- Personal experience
