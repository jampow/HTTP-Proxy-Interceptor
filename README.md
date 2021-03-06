# HTTP Proxy Interceptor

## Install

To make it easy, get [cpan minus](http://search.cpan.org/~miyagawa/App-cpanminus-1.7001/lib/App/cpanminus.pm).

### Dependencies

```shell
sudo cpanm Moose LWP::UserAgent Data::Printer Config::Any File::Slurp URI URI::QueryParam Getopt::Long Net::Server
```

## How to use

* Copy the file ```urls.json.example``` to ```urls.json```;
* Write your roles in urls.json, there is three diferent types;

```javascript
{
  // getting a local file
  "http://www.site.com.br/js/script.js" : {
      "file" : "/path/to/my/local/script.js"
  },

  // getting a file from other server
  "http://www.site.com.br/logo.jpg" : {
      "url" : "http://www.anothersite.com.br/logo.jpg"
  },

  // replacing relative path for a local path
  "http://www.site.com.br/resources/(?<caminho>.+)" : {
      "relative_path" : "/my/local/copy/resources/"
  }
}
```

* Start it! ```perl proxy-sem-ssl.pl```;
* Set the browser to pass by proxy server ```http://localhost:9999```.