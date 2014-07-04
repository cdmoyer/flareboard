##What is Flareboard?

Flareboard is the way to get your [CloudFlare](http://www.cloudflare.com) stats
to display in your [StatusBoard](http://www.panic.com/statusboard). It has been
designed to be very easy to install and use. It requires no third-party gems,
and can be run on any version of ruby from 1.8.7 to 2.1.1.

**Note**: For compatibility with 1.8.7. you *will* have to install the JSON gem.
Also, you have my sympathies for having to use 1.8.7.

##Configuration

You can edit the config hash right in the script, or you can create a config
file in your home directory named .flareboard.rc. If you create a config,
that will override the hash created in the script, which is good because it's
prepopulated with example data. It is *highly* recommended to use a config file.

### :title
The title that will show up on your status board

### :token
Your Cloudflare token - available via their website at
https://www.cloudflare.com/my-account

### :email
The email you have registered with cloudflare. **NOT** your username!

### :interval
Interval Values - see https://www.cloudflare.com/docs/client-api.html for
latest.

    20-40 only update once a day - it is no use polling more often than that
    20 = Past 30 days
    30 = Past 7 days
    40 = Past day
    !!! Anything higher than this requires a paid CloudFlare account !!!
    !!! This also enables greater than daily updates !!!
    100 = 24 hours ago
    110 = 12 hours ago
    120 = 6 hours ago

### :sites
Sites have a site specific title, a URL, and a color for the graph.
Colors: yellow, green, red, purple, blue, mediumGray, pink, aqua, orange, lightGray

Here is an example config file, using the same data as the example hash. 

    ---
    :token: XXXXXXX
    :email: user@example.com
    :sites:
    - :title: 'Should I Use That In Prod'
      :url:   'shouldiusethatinprod.com'
      :color: 'red'
    - :title: "It's Not Rocket Science"
      :url:   'itsnotrocketscience.info'
      :color: 'purple'
