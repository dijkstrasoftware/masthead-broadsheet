# Broadsheet

A newspaper theme for [Masthead](https://masthead.site). Serif headlines,
hairline column rules, a proper masthead and a section rail with dropdowns.

## The front page builds itself from tags

You do not list stories on the front page. You define **bands**, and each band
pulls the latest posts carrying one tag. Publish a post tagged Business and it
appears in the Business band on its own.

A band has a title, a tag, a layout (`three across`, `four across`,
`two across`, `ledger`, `opinion strip`), a count, and an optional *More* link
to the section front. Leave the tag empty and the band shows the latest posts
regardless of tag.

The **lead story** works the same way: give it a tag such as Lead and the newest
post carrying it becomes the splash — you promote a story by tagging it, and it
never shows up twice on the page. Its picture, caption, kicker and byline come
from the post's own options (below); fill any of them in on the front page to
override it there only. Leave the tag empty to write the lead by hand instead.

**Section fronts** lock to a tag too, so /business is just a Section front page
with its tag set to Business. Leave the tag empty and it lists everything with a
tag filter across the top.

### Writing a tag in a settings field

Type it the way you wrote it on the post. `Business`, `business` and
`  BUSINESS  ` all work; so do `The Economy` and `Asia Pacific`.

Behind the scenes Masthead slugs a tag by lowercasing it and turning runs of
punctuation and spaces into hyphens, and the theme puts what you type through
the same treatment before matching. Two cases it cannot recover, because the
platform throws the characters away when it makes the slug:

- **Ampersands are dropped, not spelled out.** `Film & TV` becomes `film-tv`.
  Typing `Film & TV` works; typing `Film and TV` does not.
- **Accents are stripped, not folded.** `Cafe` is fine; a tag written with an
  accented letter loses that letter from its slug entirely, so avoid accents in
  tag names.

A tag that matches nothing renders an empty band, which is to say nothing at
all — so a silent band is a misspelled tag. To see every tag actually in use,
open a Section front with no tag set: the filter chips across the top are the
full list.

## Story options

Every post carries its own options, so you set things once on the story rather
than on every page that promotes it.

- **Featured image**, with alt text and a **caption**: printed under the
  headline and used as the lead's picture. It also shows as a thumbnail in the
  front page's grid bands (switch off per band with *Show pictures*), in Section
  fronts set to grid and in the magazine's latest band. Ledgers and the opinion
  strip stay text only.
- **Kicker**: the small label over the headline. Empty means the first tag,
  which is what you want unless that tag is a promotion tag like Lead.
- **Byline**: printed in the article's meta line, under the lead, and as the
  author's name in the opinion strip.

Plain pages get a kicker, a standfirst, a wide layout and a switch to hide the
masthead.

## Page types

Set any of these as your homepage.

- **Front page** — a lead and bands, both pulled from tags.
- **Briefing** — timestamped bulletins with a side rail, then a tag-scoped post
  list. For live news. Bulletins file themselves: every post tagged Live (or
  whatever tag you set) becomes one, stamped with its publish time. Pinned
  bulletins you write by hand sit above them, and nothing appears twice.
- **Magazine** — one full-bleed cover story and features with big pictures. Laid
  out by hand, because pictures are the point.
- **Section front** — one tag, as a ledger or a grid.

## Navigation

The section rail is one list under Navigation. Leave *Drops down under* empty for
a top-level section; fill it with another section's label to nest it into that
section's dropdown. Dropdowns are CSS only — on touch screens the children
flatten into the scrolling rail instead. The same list prints as the footer
columns.

## Preview

Broadsheet renders against Masthead's `v1` contract, so it needs masthead CLI
0.4.0 or later.

```
masthead preview
```
