Spineless.js a simple MVC without the need of a backbone
=========

Spineless is designed for small sites and prototypes that need to be built quickly without much of a infrastructure. 

Dependencies
------------
Spineless has only two dependencies which is Mustache.js and JQuery.

How to be spineless
-------------------

Mustache uses the concept of controllers and views and partials (called templates). The best way explain spineless is to use it. Consider the following example:
`
      <body>
        <h1>Welcome to the hello world application</h1>
        <div class="application">
          <div class="controller" data-controller='application'>
            <div class="view" data-action='index'>
              <!-- the next line calls the sideNav template -->
              <div style="float:left;" data-template='sideNav'></div>
              <div style="float:left;">
                 &lt;-- click a link on the side nav.
              </div>
            </div>
            <div class="view" data-action='hello'>
              <!-- again we reuse the sideNav template -->
              <div style="float:left;" data-template='sideNav'></div>
              <h1>HELLO!!!!</h1>
            </div>
          </div>
        </div>
        <div class="templates">
          <div data-template-name='sideNav'>
            <ul>
              <li><a class="route" href="/">Home</a></li>
              <li><a class="route" href="/application/hello">Hello</a></li>
            </ul>
          </div>
        </div>
        <script src="../lib/jquery-1.7.1.min.js" type="text/javascript" charset="utf-8"></script>
        <script src="../lib/jquery.mustache.js" type="text/javascript" charset="utf-8"></script>
        <script src="../spineless.js" type="text/javascript" charset="utf-8"></script>
        <script type="text/javascript">
          $(document).ready(function(){
            var sp = $.spineless();
            sp.render('application', 'index');
          });
        </script>
      </body>
`

TODO
====
Improved routing engine as described in this proposed routing API:
https://gist.github.com/84e8f173925b81cb20eb

Authors
=======

Mark Daggett @heavysixer, humansized.com
