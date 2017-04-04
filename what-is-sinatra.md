# What is Sinatra?

The horoscope app only uses a single page and \(when you've finished this tutorial\) 2 different requests. Ruby on Rails, the web application framework you may be more familiar with, makes a lot of assumptions about the kind of applications being built with it. It assumes you're going to be using a database and at least a few different requests, at a minimum. We don't need any of that. Sinatra makes none of these assumptions so it's perfect for this kind of application.![](/assets/Screen Shot 2017-04-04 at 12.26.11 AM.png)

Here's the entirety of horoscope.rb, which contains all of the backend logic for the application. Since '/' is the url for the home page, this file is setting up a homepage that has access to a variable called `@prediction`. It uses a template file called `index.erb.`

With Sinatra, you can do a lot with very few lines of code. You can define any request in Sinatra by adding a block to this file. For example, if we wanted to add a page with the url '/

