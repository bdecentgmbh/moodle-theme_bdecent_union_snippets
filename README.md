# SCSS snippets for Boost Union

SCSS snippets by [bdecent GmbH](https://bdecent.de) for the Moodle theme
[Boost Union](https://moodle.org/plugins/theme_boost_union).

This repository works exactly like the
[community snippets repository](https://github.com/moodle-an-hochschulen/moodle-theme_boost_union_snippets)
and is meant to be used **in addition** to it, not instead of it. Every snippet carries the
metadata header from the community
[boilerplate](https://github.com/moodle-an-hochschulen/moodle-theme_boost_union_snippets/blob/main/boilerplate/boilerplate.scss),
so Boost Union reads them without any further configuration.

Like the community repository, this one is structured by snippet goal, with each goal having a
top level folder.

## Snippets

| Snippet | Goal | Scope | What it does |
|---|---|---|---|
| [`eyecandy/slim_menubar.scss`](eyecandy/slim_menubar.scss) | eyecandy | global | Turns the Boost Union smart menu bar into a slim, compact bar with a dark background and right-aligned menu items. Every vertical offset which Boost Union derives from the menu bar height — page content, left, right and message drawers, drawer togglers, the navbar below — is recalculated from a single height variable, so the layout stays intact. |
| [`easeofuse/course_reports_cards.scss`](easeofuse/course_reports_cards.scss) | easeofuse | course | Turns the plain link list on the course reports page into a responsive grid of cards with a recognisable icon per report. |
| [`easeofuse/course_reuse_cards.scss`](easeofuse/course_reuse_cards.scss) | easeofuse | course | The same card grid for the course reuse page — import, backup, restore, copy and reset. |
| [`easeofuse/participants_filter_collapsed.scss`](easeofuse/participants_filter_collapsed.scss) | easeofuse | course | Collapses the filter form on the enrolled users page into a small filter icon, because filtering participants is only needed in large courses. |
| [`easeofuse/course_management_subtle_actions.scss`](easeofuse/course_management_subtle_actions.scss) | easeofuse | global | Dims the action icons on the course and category management page and brings them back as soon as you point at, or tab into, the row they belong to. The selected category and course keep their icons at full strength. |
| [`easeofuse/course_management_detail_panel.scss`](easeofuse/course_management_detail_panel.scss) | easeofuse | global | Makes the course details on the course management page visible on selection instead of opening them below the fold: a sticky third column on wide screens, a sticky side column on laptops and a panel above the listings on narrow screens. |

Every snippet is configurable through SCSS variables at the top of the file. They are declared
with `!default`, so you can override any of them in Boost Union's *Raw initial SCSS* setting
without editing the snippet itself.

## Snippets and Moodle versions

SCSS snippets carry no information about the Moodle version they were written for. Boost Union
applies every enabled snippet regardless of the Moodle version, and the only version information
in a snippet is the free-text `Tested on` header, which is shown to admins but never evaluated.

That matters because snippets depend on Moodle's core markup, which changes between releases. A
snippet written against Moodle 5.2 can therefore do nothing, or occasionally the wrong thing, on
Moodle 4.5.

If you need to serve several Moodle versions, either branch this repository per Moodle version
(`MOODLE_405_STABLE`, `MOODLE_502_STABLE`, ...) or keep one folder per version. `local_busnippets`
supports the placeholders `{moodlebranch}` and `{moodleversion}` in its archive URL and
subdirectory settings for exactly this, so that a single setting value works on every site.

## Installation

### By hand

1. Download this repository as a ZIP file.
2. Go to *Site administration ▸ Appearance ▸ Boost Union ▸ SCSS snippets ▸ Settings*.
3. Switch *Enable uploaded snippets* on.
4. Upload the ZIP file. Boost Union unpacks it and picks up the contained snippets.
5. Go to the *Overview* tab and enable the snippets you want.

### Automatically

If you run more than one site, [`local_busnippets`](https://github.com/bdecentgmbh/moodle-local_busnippets)
syncs this repository into Boost Union with a scheduled task, so that every site carries the same
snippet library without anyone uploading a ZIP file by hand.

## Notes

- Snippets are identified by their **file name**. Do not rename a file unless you accept that
  Boost Union will treat it as a new snippet, which starts out disabled.
- The file names in this repository are chosen so that they do not collide with the community
  snippets repository. Both end up in the same file area, so a collision would mean one snippet
  silently overwriting the other.
- The snippets are written against **Moodle 5.2 / Boost Union 5.2**. Earlier or later versions may
  need adjustments, mostly because they depend on Moodle's core markup, which changes over time.

## Contributing

Snippets are welcome. Please use the community
[boilerplate](https://github.com/moodle-an-hochschulen/moodle-theme_boost_union_snippets/blob/main/boilerplate/boilerplate.scss)
for the metadata header, put the file into the folder of its goal and make sure the file name is
unique. A preview image with the same base name and the extension `webp`, `png`, `jpg`, `jpeg` or
`gif` next to the snippet is shown in Boost Union's snippet overview.

## License

[GNU GPL v3 or later](https://www.gnu.org/copyleft/gpl.html)
