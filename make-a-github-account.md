# Make a GitHub account

![](/assets/Screen Shot 2017-03-29 at 11.59.06 PM.png)
If you don't have a GitHub account, you'll need to create one first at [https://github.com/join](https://github.com/join) (the free version will be fine\). Then go to https://github.com/spinecone/api-horoscope.

The template we're going to base a new project on, API Horoscope, is made up of 8 files \(one of them is not included on GitHub. I'll explain why further down\).

* **README.md** is a file that most GitHub repos have. It describes what the project does and how to use it.
* **Gemfile** is a list of external libraries (gems) we will be using in this project. We'll talk about what each of these 4 gems will be used for in a later chapter.
* **Gemfile.lock** is a snapshot of the versions of the gems our project uses. You can read more about Gemfile and Gemfile.lock [here](http://bundler.io/v1.3/rationale.html).
* **horoscope.rb** handles all of the backend logic of our project. It decides what text will go into the horoscope message.
* **style.css** (in the **public** directory) controls the colors and fonts used in this project. Feel free to change this if you aren't a big fan of purple 🙂
* **index.erb** (in the **views** directory) defines the visual contents of project. Right now this is just a box with a horoscope message and a "Try Again" link that refreshes the page.
* **layout.erb** (also in the **views** directory) defines the overall layout of the page. You won't need to change this at all.
* Finally, **.env** will hold our authentication secrets which we'll cover in the section about environment variables. **.env** is not included in the template repo since we don't want to make our authentication info publicly accessible.

## What did we just do? {#what-did-we-just-do}

GitHub is a service that allows us to share projects with others. It uses Git, a program for keeping track of changes to a project. There's nothing about Git or GitHub that's specific to programming. You could use it to keep track of changes to a novel or any other project you might want to share with other people, as long as it can be represented as a group of files. For this tutorial, we're going to be taking "api-horoscope," a basic Sinatra app that's hosted on GitHub, copying it, and adding two API integrations to it.

Git and GitHub are very complex and have a lot of different features that we won't be covering in this tutorial. If you're interested in getting started with Git and GitHub, I highly recommend the [Don't Be Afraid to Commit](https://dont-be-afraid-to-commit.readthedocs.io/en/latest/) tutorial.



