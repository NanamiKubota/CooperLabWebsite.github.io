# Cooper Lab Website

- [Cooper Lab Website](#cooper-lab-website)
  - [Update December 2024](#update-december-2024)
  - [Update December 2023](#update-december-2023)
  - [Major updates 12-2022](#major-updates-12-2022)
- [Lab website documentation for future edits](#lab-website-documentation-for-future-edits)
  - [How to update](#how-to-update)
    - [Adding People](#adding-people)
  - [Website structure](#website-structure)
    - [Updating lab roster](#updating-lab-roster)
    - [Other customization](#other-customization)
  - [Using Jekyll](#using-jekyll)


## Update December 2024

- Update lab members
- Update Vaughn's bluesky handle to new handle
- Update documentation on how to update website

## Update December 2023

- Add new lab members
- Replaced Twitter/X with Bluesky and LinkedIn

To do
- Get missing lab member profile
- Add publication page
- Update research area page?


## Major updates 12-2022
 - Changing jekyll theme to minimal mistakes
 - Home page
   - Replaced with lab logo and mission statement
 - People
   - Current lab members and alumni members are under People tab
   - Added missing current and alumni members
 - Contact
   - Updated contact page
   - Updated format
 - Research
   - Updated format

<br>

***

# Lab website documentation for future edits

The lab website was created using [Jekyll](https://jekyllrb.com/), specifically the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme. Most questions on syntax, navigation, layouts, etc. can be found there. There are a few custom layouts and structures implemented into this website which I will cover in a later section. This new lab website was developed under a [forked repository by Nanami](https://github.com/NanamiKubota/CooperLabWebsite.github.io) which was merged to the [CooperLabWebsite newlabwebsite22 branch](https://github.com/CooperLabWebsite/CooperLabWebsite.github.io/tree/newlabwebsite22), NOT the master branch (as of December 12, 2022).

To have an easier time editing the website and previewing it on your local browser, I recommend creating your own GitHub account, installing Git onto your computer, and installing an integrated development environment (IDE) like [Visual Studio Code (VSCode)](https://code.visualstudio.com/) onto your own computer. Then set up Git in VSCode followed by Jekyll ([instructions for Jekyll installations are here](https://jekyllrb.com/docs/)). If everything is properly set up, you can run `bundle exec jekyll serve` on the terminal within VSCode and a preview of the website should be hosted locally at http://localhost:4000. 

**Note**: sometimes the website may look okay locally but fail or look different once it gets published through GitHub Pages. When this happens, go back and fix the bugs locally before trying again. The website may also have a few minutes to launch the new edits.

## How to update

To avoid making edits to the actual branch where the website is hosted on, fork the repo (specifically the newlabwebsite22 branch) to get started. Once you have that forked, use your preferred IDE (I use VSCode) to start editing the files.

### Adding People

To add people to the current or alumni webpage, create a markdown file (.md) and populate the appropriate fields. A template can be found in the [templates folder, "profile_templates.md"](https://github.com/NanamiKubota/CooperLabWebsite.github.io/blob/main/templates/profile_template.md). Remember to rename the markdown file with the first and last name of the person. The beginning of the markdown file should look something like this:

```
---
title: Nanami Kubota
position: PhD Student
contact: nanami.kubota@pitt.edu
publications: 
image: /images/nanami_kubota.jpeg
collection: current
group: grad
links:
    CV:
    Email: "mailto:nanami.kubota@pitt.edu"
    Publications: "https://scholar.google.com/citations?user=B1-vMZEAAAAJ&hl=en&oi=ao"
    Twitter: "https://twitter.com/NanamiKubota"
    Website: "https://nanamikubota.github.io/"
year-start: 2021
year-end: present
---
```

This is called a YAML header. The YAML header is between two --- lines. Please do not delete these lines. The values within the header can be used to populate different contents within the website or categorize the person by a value. For example, these are what each field means for each lab member's markdown file:
- title: name of the person
- position: lab position of the person (e.g. Postdoctoral Researcher, PhD Student, Undergraduate Researcher, etc.)
- contact: email address of person
- image: relative filepath to the person's profile picture. If the picture is in the "images" folder, then the relative filepath will be "/images/profile_picture_filename.png". The file format can be png, jpeg, jpg, etc. as long as it is a picture.
- collection: denotes the collection that the profile belongs to. This collection tag is used to categorize and find profile pictures when called as a function. Use "current" for current lab members and "alumni" for alumni members.
- group: custom tag/marker to further categorize from collection. Used in a function when grouping specific profile pictures together. The following groups are available: 
  - "grad" = for graduate students
  - "undergrad" = for undergrads
  - "postdoc" = for postdocs
  - "PI" = for PI (Vaughn)
  - "staff" = for research staff
  - "hs" = for high school students
- links: used for the icons found underneath the profile picture for current lab members
  - CV: link to CV (such as a google doc)
  - Email: Use "mailto:yourPittID@pitt.edu" format so that an email draft is made addressed to the person on click.
  - Twitter: link to twitter account *outdated: please use Bluesky*
  - Website: link to personal website or other
  - Bluesky: link to Bluesky
- year-start: the year that the person started in the lab (which is viewable in the alumni page). The alumni page sorts profiles in reverse chronological order using this value.
- year-end: the last year that the person was in the lab (or "present" for current members; also viewable in the alumni page)
- present-position: for alumni lab members for the purpose of sharing their current/next position after leaving the Cooper lab.

Below the YAML header (below the three dash lines; ---), enter a short introduction of the person. If you want to format certain text (e.g. bold, hyperlink, etc.) use HTML or markdown shortcuts. Some commonly used ones are:

- Bold: `<b>insert bolded text here</b>`
- Italics: `<i>insert italicized text here</i>`
- Hyperlink: `[words to hyperlink](https://your-link-here.com)`


## Website structure

Familiarize yourself with markdown files, css, html, and a little bit of YAML to make it easier to navigate the files.

### Updating lab roster

For general updates to the lab roster, you will probably only need familiarity with the _alumni, _current, images, and templates folders. To create a new profile, copy an existing markdown profile or use the template under the templates folder to get started. Pictures should be stored under the images folder. To move members from the current to alumni section, simply drag their markdown file from _current to _alumni.

### Updating research area page

To update the research area page, go to /_pages/research.md and update the text as needed. The file follows the markdown format so refer to online resources to make stylistic changes. Make sure to update the table of contents too.

To add pictures, make sure to save pictures under the /images/ folder. Then, use the following html format to add pictures:

```html
<div class="research_fig">
    <img src="/images/filename.jpg" />
    <p>Enter figure legend here. You can <i>italicize</i> and add
    <a href="https://micropopbio.org/"> links</a> like this.</p>
</div>
```

### Other customization

To make more major changes to the website will require some understanding in Jekyll, CSS, HTML, YAML, and markdown.

## Using Jekyll

To run the website locally, run:
```
bundle exec jekyll serve
```

This should allow you to preview the website locally at http://127.0.0.1:4000.

Refer to this website for more info: https://jekyllrb.com/tutorials/using-jekyll-with-bundler/