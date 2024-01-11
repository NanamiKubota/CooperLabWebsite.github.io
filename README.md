# Cooper Lab Website

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


## TO DO
- Get missing profile pictures

<br>

***

# Lab website documentation for future edits

The lab website was created using [Jekyll](https://jekyllrb.com/), specifically the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme. Most questions on syntax, navigation, layouts, etc. can be found there. There are a few custom layouts and structures implemented into this website which I will cover in a later section. This new lab website was developed under a [forked repository by Nanami](https://github.com/NanamiKubota/CooperLabWebsite.github.io) which was merged to the [CooperLabWebsite newlabwebsite22 branch](https://github.com/CooperLabWebsite/CooperLabWebsite.github.io/tree/newlabwebsite22), NOT the master branch (as of December 12, 2022).

To have an easier time editing the website and previewing it on your local browser, I recommend creating your own GitHub account, installing Git onto your computer, and installing an integrated development environment (IDE) like [Visual Studio Code (VSCode)](https://code.visualstudio.com/) onto your own computer. Then set up Git in VSCode followed by Jekyll ([instructions for Jekyll installations are here](https://jekyllrb.com/docs/)). If everything is properly set up, you can run `bundle exec jekyll serve` on the terminal within VSCode and a preview of the website should be hosted locally at http://localhost:4000. 

**Note**: sometimes the website may look okay locally but fail or look different once it gets published through GitHub Pages. When this happens, go back and fix the bugs locally before trying again. The website may also have a few minutes to launch the new edits.

## How to update

Avoid making edits to the actual branch where the website is hosted on, and instead fork and create a new repo of the newlabwebsite22 branch to get started. Once you have that forked, use your preferred IDE (I use VSCode) to start editing the files.

### Adding People

To add people to the current or alumni webpage, create a markdown file (.md) and populate the appropriate fields. I recommend just copying and pasting a markdown file from the "_current" folder to use as a template. Remember to rename the markdown file. The beginning of the markdown file should look something like this:

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

This is called a YAML header. The values within the header can be used to populate different contents within the website or categorize the person by a value. For example, these are what each field means for each lab member's markdown file:
- title: name of the person
- position: lab position of the person (e.g. Postdoctoral Researcher, PhD Student, Undergraduate Researcher, etc.)
- contact: email address of person
- publications: old field leftover from old website (you can leave this blank)
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
  - Twitter: link to twitter account
  - Website: link to personal website or other
- year-start: the year that the person started in the lab (which is viewable in the alumni page). The alumni page sorts profiles in reverse chronological order using this value.
- year-end: the last year that the person was in the lab (or "present" for current members; also viewable in the alumni page)

Below the YAML header (below the three dash lines; ---), enter a short introduction of the person. If you want to format certain text (e.g. bold, hyperlink, etc.) use HTML or markdown shortcuts. Some commonly used ones are:

- Bold: `<b>insert bolded text here</b>`
- Italics: `<i>insert italicized text here</i>`
- Hyperlink: `[words to hyperlink](https://your-link-here.com)`


## Website structure

Familiarize yourself with markdown files, css, html, and a little bit of YAML to make it easier to navigate the files.

To be updated.


## Using Jekyll

To run the website locally, run:
```
bundle exec jekyll serve
```

This should allow you to preview the website locally at http://127.0.0.1:4000.

Refer to this website for more info: https://jekyllrb.com/tutorials/using-jekyll-with-bundler/