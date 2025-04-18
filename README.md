# hust-workshop.github.io

HUST Workshop at Supercomputing

# Join the Community

Please join the HUST Slack Community by contacting Elsa Gonsiorowski at ``gonsie@me.com``.

The Slack Workspace is called: https://hpcusersupporttools.slack.com

## Layout of this repo

This site uses sections within a single page, where each page is particular year.
The sections come from the files in the `_posts` folder.
The date in the file name determines on which page the text will appear.

### Year Page

To create a page for all the sections of a single year, use the following (with the appropriate year):

```
---
layout: default
year: 20XX
---
```

### Page Sections

The sections of the page are posts within that year and appear in reverse-date order (oldest appear at the top).

The organization of the sections is:
- `20XX-01-01-intro.md`: Site intro.
- `20XX-01-02-program.md`: Workshop program.
- `20XX-01-03-topics.md`: Workshop topics.
- `20XX-01-04-submissions.md`: Submission format.
- `20XX-01-05-dates.md`: Deadlines.
- `20XX-01-06-committee.md`: Names and institutions of the committee members.
- `20XX-01-07-slides.md`: Links to the presentation slides.
- `20XX-01-08-history.md`: Links to past proceedings.

Create sections by adding files within the `_posts` directory.
Hide existing sections by adding the following to the pages's yaml front matter:

```
display: false
```

### Icons

The icons included between each section come from [font awesome](https://fontawesome.com).
We are using [version 4.2.0](https://fontawesome.com/v4.7.0/cheatsheet/), but that could easily be changed by updating the [version downloaded by the layout](https://github.com/hust-workshop/hust-workshop.github.io/blob/f3467c98171d8e8e4277f7f63fc000bb5ed4cebc/_layouts/default.html#L11).

## Setting up a New Year

Tasks to do for a new year:
1. Archive the current year by moving the index page. 
The following assumes you are running in the "new" year:
```bash
mv index.md archive/$(date -d -1year +%Y)-index.md # on Linux
mv index.md archive/$(date -v -1y +%Y)-index.md # on mac
```
2. Create this year's page at the top level
```bash
echo -e "---\nlayout: default\nyear: $(date +%Y)\n---" > index.md
```
3. Duplicate files in the `_posts` directory for the new year.
In the posts directory, each filename must have the format `YEAR-MO-DY-slug.md` (the "slug" does not really matter). 
Each of these files becomes a "section" on the single-page website.
The dates determine the order in which the sections appear, with only posts matching the `year: ` entry in the index file's frontmatter appearing on that particular page.
The current practice is to use the "day" to mark the order we'd like.

Copy over specific files one-by-one from the previous year and update the contents as you go.
Note that some sections `20XX-01-02-program.md` don't get created until later in the timeline, but by having the day "02" are put near the top of the page.

## Theme Source

This is a compressed-commit version of
[github.com/t413/SinglePaged](https://github.com/t413/SinglePaged)
