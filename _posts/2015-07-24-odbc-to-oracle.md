---
layout: post
title: "ODBC to Oracle"
categories: blog
excerpt: "What a pain in the ass! Have I told you how much I hate Oracle?"
tags: [ODBC, Oracle, Windows]
date: 2015-07-24
comments: true
share: true
---

What a pain in the ass! Have I told you how much I hate Oracle?

Googling *"Oracle ODBC"* will point you to an Oracle website with drivers dated a decade ago.

![Oracle ODBC Drivers Download](http://res.cloudinary.com/ianliew/image/upload/v1438653266/w0qani.png)

But when you click on `What's New` and click back on `Downloads` again ...

![Oracle Database on Windows Downloads](http://res.cloudinary.com/ianliew/image/upload/v1438653467/tggmv4.png)

A completely different page emerged with links to items you'd actually want. For convenient sake, link to page [here](http://www.oracle.com/technetwork/database/windows/downloads/index.html).

Download and install the `Oracle Data Access Components and Tools - .NET and Windows`. After installation, you should have the following in your list of drivers.

![ODBC Data Source Administrator](http://res.cloudinary.com/ianliew/image/upload/v1438654115/tonszl.png)

But upon adding a new `Data Source` (within `System DSN`), the limited options here will most likely not allow you to successfully connect to an Oracle DB.

![Oracle ODBC Driver Configuration](http://res.cloudinary.com/ianliew/image/upload/v1438654535/jb5slj.png)

For better control of the connections string, you'd have to edit the `tnsnames.ora` file in `C:\app\client\<username>\product\12.1.0\client_1\Network\Admin`. A sample file is provided in the `Sample` directory, but here's one you can reference.

{% highlight yaml %}
alias =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = myserver.mycompany.com)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = orcl)
    )
  )
{% endhighlight %}

With that you should be able to get a `TNS Service Name` with the defined `alias` in the drop down list, which you can now use to connect to the Oracle DB.
