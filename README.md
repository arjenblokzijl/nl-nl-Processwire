# Dutch language pack for ProcessWire

Dutch (nl_NL) language pack for [ProcessWire](https://processwire.com): translations of the
ProcessWire core admin, the files in `wire/`. Modules from outside the core (in `site/modules/`)
aren't included.

## Coverage

Made for **ProcessWire 3.0.270**. The pack has a translation for every phrase in the core at that
version: 4,745 phrases in 220 files. Translations are matched on their English text, so they also
work in older and newer 3.x versions, for every phrase that hasn't changed.

The translations use informal Dutch ("je"), as the 2015 pack did. CMS terms follow that pack too:
Pagina, Veld, Template, Kinderen (subpagina's), Bovenliggende pagina, Prullenbak, Rol, Permissie,
Instellingen (Setup).

## Installation

1. In the admin, go to Setup > Languages and edit the language that should be Dutch.
2. Upload all `.json` files to "Core Translation Files" (you can select or drop them all at once)
   and save.

The admin follows each user's language (in their profile), so users of this language get the
Dutch admin. If Dutch is your default language, that's every user who hasn't chosen another one.

A few phrases are settings rather than text, and the pack sets them for Dutch:

- The locale `nl_NL.UTF-8` (LanguageSupport); the server needs that locale installed.
- The Dutch language files of CKEditor, TinyMCE, the jQuery UI datepicker and the timepicker.
- Dutch month and day names and abbreviations, and relative dates ("3 weken geleden").
- Defaults for **new** Datetime fields use 24-hour time (`j F Y H:i`, `H:i`). Existing fields keep
  their own formats. Every other date format stays as in the core (e.g. `Y-m-d`), because code
  parses those.

## How this version was made

The 2015 version of this pack translated about 400 phrases, written for ProcessWire 2.5 and 2.6.
This update, from November 2026, was made with [Claude](https://claude.ai) (Anthropic's AI
assistant) and [DeepL](https://www.deepl.com):

1. **The 2015 translations** were kept for every phrase whose English text hasn't changed since,
   about 280 phrases. Ten files that ProcessWire 3 moved got their new paths; without those, they
   no longer loaded. The same translations were reused wherever the same English phrase appears
   in another core file (the admin menu, for example, now comes from `AdminThemeFramework.php`),
   and their spelling mistakes were fixed.
2. **DeepL** translated the remaining 4,244 phrases. Each request carried the file it came from as
   context, informal address, and a glossary for the CMS terms above. Placeholders (`%s`, `%1$d`,
   `{name}`), code, URLs and HTML were shielded from translation, and every result was checked
   to contain exactly the placeholders of the English phrase.
3. **Claude** wrote the scripts, ran them, and reviewed the result. It read all 1,082 short labels
   (one or two words, where DeepL has the least context), every phrase that is a setting, and the
   longer phrases of the modules editors use most: the page tree, the page editor, repeaters, the
   file and image fields, and the link dialog. That led to about 270 corrections, such as
   "Right" (Juist → Rechts), "Page List" (Paginavergelijking → Paginalijst), "second"
   (tweede → seconde), and date formats DeepL had "translated" (`Y-m-d` → `j-m-d`).

The result was then checked in a running ProcessWire 3.0.270 admin: login, page tree, page
editor, image and file fields, link dialog, Setup, modules, users and profile.

**Not every phrase was read by a person.** Most of the longer DeepL translations, especially in
the less used parts of the admin (comments, export/import, the system updater), haven't been
reviewed. If you find a translation that's wrong or reads oddly, please open an issue or a pull
request.

## Credits

The repository was originally created by Jasper Metselaar ([formmailer](https://github.com/formmailer)).
From March 2015 it was maintained by Arjen Blokzijl ([arjenblokzijl](https://github.com/arjenblokzijl)).
Their translations are still part of this pack.
