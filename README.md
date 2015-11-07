## CGI-Login

So this is a Simple user Login system implemented using `CGIHTTPServer` with `sqlite3` as the db.

`reg_no`, `username`, `password` are entered by the user and queried to `sqlite3` to check whether the user with the particular `reg_no` exists or not in the `user_base.db`

If the user exits, redirect the `index.html` to a page which displays the particular users details like `username` and `reg_no` upon successful login.

If the user does not exist. Ask him, if he wants to create an account,if yes update the db accordingly

##Usage

![Usage](https://raw.githubusercontent.com/prodicus/cgi_login/master/cgi_login_demo.gif)

## File structure. 

```bash
.
├── cgi-bin
│   ├── create_db.py
│   ├── user_base.db
│   └── user_check.py
├── index.html
├── LICENSE
└── README.md
```

The `cgi` scripts should reside in `cgi-bin` or `htdocs` folder otherwise they wont be executed. Remember to make the scripts executable. Now the `user_base.db` file should also have read and write operations for the other users too as `SQLite3` needs those permissions to create a lock on the db file. So do a 

`$ chmod 755 *`

inside the `cgi-bin` directory

## Running `CGIHTTPServer` 

Now you can use a full blown server software like `apache2` or `nginx` trying this out. But for this example, I have done it using `CGIHTTPServer` provided by default with the `python` distribution.

To run it, first clone the repo and inside a folder, let's say `cgi_scripting` in your `home` directory.

```bash
$~/cgi_scripting$ python -m CGIHTTPServer
Serving HTTP on 0.0.0.0 port 8000 ...
```

Now go to your browser and type the url [http://localhost:8000/](http://localhost:8000/) and it would serve you `index.html`.

##License

[Apache license](https://github.com/prodicus/cgi_scripting/blob/master/LICENSE)
