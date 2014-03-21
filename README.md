# middleman-blog-bootstrap-template

This is a [Middleman](http://middlemanapp.com) template speed up building blog.
It encourages asset management with [Bower](http://github.com/twitter/bower) and includes a default bower.json. 
Select the themes from [Bootswatch](http://bootswatch.com/), then you can easily build bootstrap-based blogs.

##Features:
* Rendering engine
 - [Markdown](http://daringfireball.net/projects/markdown/) in posts
 - [Slim](http://slim-lang.com/) in layout
* Middleman plugins
 - [middleman-blog](http://github.com/middleman/middleman-blog/)
 - [middleman-livereload](http://github.com/middleman/middleman-livereload)
 - [middleman-target](http://github.com/xunker/middleman-target) 
 - [middleman-deploy](http://github.com/tvaughan/middleman-deploy) config snippet to ease FTP/SFTP deployment
* [Bower](http://github.com/twitter/bower) package management
 - [Normalize.css](http://necolas.github.com/normalize.css) 
 - [Modernizr](http://modernizr.com)
 - [Bootswatch](http://bootswatch.com/)
 - [Font-awesome](http://fontawesome.io/)
 - [jQuery](http://jquery.com/)
 - [Respond.js](http://github.com/scottjehl/Respond)
* [SCSS](http://sass-lang.com)
* [Coffeescript](http://coffeescript.org/)

[Preview](source/images/sample-theme-flatly.png) the sample image which is made in Bootswatch "flatly" theme.

##Installation
1. If you're just getting started, install the `middleman` gem and generate a new project:
```
gem install middleman
```
2. Download/clone to: 
```
/.middleman/blog-bootstrap`
```

3. Create your new Middleman project with thie template:
```
middleman init my_new_project --template=blog-bootstrap
```
4. Install the assets in the `bower_components/` directory.
```
bower install
```
*Note: You can name the template whatever you like, so long as you call the same name in the `middleman init` command*

##Configuration
Edit `config.rb` as you like.

1. Edit site settings
```
# Set site setting, used in helpers / sitemap.xml / feed.xml.
set :site_url, 'http://blog.url.com'
set :site_author, 'Blog author'
set :site_title, 'Blog title'
set :site_subtitle, 'Blog subtitle'
# Select the theme from bootswatch.com.
# If false, you can get plain bootstrap style.
# set :theme_name, 'flatly'
set :theme_name, false
# set @analytics_account, like 'XX-12345678-9'
@analytics_account = false
```

2. Add packages with bower
By default, all bower packages are put in the ```bower_components/``` directory outside of the source. This is to prevent all of the extra files bower downloads being copied over to ```build/```.
We used to have to symlink the files we wanted in the components directory over to our assets path in ```source/```, but no longer.

Now when you want to install a package, simply ```bower install <somepackage>``` and include it like you would any other file in sprockets.

If you want to reference the asset directly in your HTML, then you will need to create a file in the asset path that includes the asset via sprockets. It's not ideal, but I think thats the best I can do right now.  An example of this is ```source/assets/js/vendor/modernizr.js``` and ```source/assets/css/vendor/universal-ie6.css```.

3. Edit SCSS
I have not included a CSS grid at this time, mostly because it seems like everyone's got their own preference, and I haven't found one I really like yet.

However, I have included a file organization that has worked for me so far:
*any variables (like colors and such) go into _settings.scss
*any packages/imports go into _imports.scss

I'll likely be tweaking this a bunch as I go, however.


##Included helpers and other goodies
I have included a few helpers to help out with organizing information on your site. They are located in ```helpers/```.

To get typekit or analytics inclusion, simply add your account name/code to the appropriate places.

Also remember to add the site name, keywords, and description in ```helpers/meta. If you want to include a page-specific one of these, they will be appended to the overall site's.

##Requirements
Confirmed in ruby 2.0.0p247, rubygem 2.0.3, middleman 3.2.2

##Contribute
Have a better idea for middleman defaults? Give it a fork! Don't hesitate to create an issue if you have a problem or question.

## License

Copyright (c) 2014 [Biblichor](http://github.com/biblichor) MIT Licenced, see [LICENSE] for details.
