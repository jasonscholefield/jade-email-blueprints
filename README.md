This set of Gulp tasks aims to remove the headache of email template creation.

---
## Features
* Jade templates
* Jade Mixins including: All sorts of table components & arrangements, Campaign Monitor's Bulletproof Buttons & Bulletproof Backgrounds
* Automatic css inlining and SASS stylesheets
* Export for Campaign Monitor or package in a zip file (WIP)
* Quick test emails through the command line (WIP)

---
#### Jade templates
HTML tables are hard to write and even harder to read. Using a preprocessor aims to alleviate that headache. I use jade mixins for tables, multi column layouts, buttons (plus bulletproof), backgrounds (plus bulletproof), and spacers so you don't get lose in the nested table nightmares.

![](https://raw.github.com/DeckardPain/jade-email-blueprints/master/github/jade.jpg)

---

#### SASS and automatic CSS inlining
Write your css in an external file and get all those styles automatically inlined. Stylesheets will also be included in the head of the file so your media queries will work nicely.

Keep your styles in an external SASS file and use variables to keep your code clean.

![](https://raw.github.com/DeckardPain/jade-email-blueprints/master/github/css.jpg)


---
#### Gulp tasks for exporting (WIP)
`gulp export` generates a version-numbered-zip-file with images and html to send to your clients and an html file with img.zip to import into Campaign Monitor. These files can be found in `export/zip` and `export/campaignmonitor`.


---
#### External data
It's easiest to work with one file for all the links and text contents. So edit all links, or any other data, in data.json and they will be placed inside your html. Access the contents of this file in your .jade files like `#{data.title}`.

```json
{
    "title": "My Fantastic Email",
    "website": {
      "title": "google.nl",
      "href": "http://www.google.com/"
    },
    "unsubscribe": "http://www.google.com/unsubscribe",
    "webversion": "http://www.google.com/webversion",
    "facebook_url": "https://www.facebook.com/",
    "twitter_url": "https://twitter.com/",
    "cta_lipsum": {
      "title": "Lorem Ipsum",
      "href": "http://www.lipsum.com/"
    }
}
```

---
#### Command line testmails (WIP)
You can test your mailing from the command line. Before you can send a test mail, create a config.json in the root of the project:

```
{
  "auth": {
    "user": "me@gmail.com",
    "pass": ""
  },
  "recipients": "me@gmail.com, me@hotmail.com"
}
```

now run 'gulp testmail' to send those emails to yourself for testing.


---
#### Basic template provided
A basic example is available for you to get you started, but feel free to start from scratch. 

![](https://raw.github.com/DeckardPain/jade-email-blueprints/master/github/responsive.jpg)

---
# Getting started
1. clone this repository
2. 'npm install'
3. 'npm install express'
3. 'gulp'

// I was having issues with express, so line 3 is a temporary fix. I'm just too lazy to fix it in the gulp file right now.

Head to `http://localhost:8000/` to view your generated html files.

Open up your text editor and start editing files in `src/`. This is where all jade, scss and image files can be found.