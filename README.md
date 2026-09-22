# note

Daily markdown notes from the terminal, with a picker in the style of [try](https://github.com/tobi/try).

One file per day (`2026-09-22-daily.md`) or per topic (`2026-09-22-topic.md`), plain markdown, nothing else.

```
note                 picker: fuzzy search + calendar
note today           today's daily note      (YYYY-MM-DD-daily.md)
note yesterday       yesterday's daily note
note tomorrow        tomorrow's daily note
note 2026-09-20      daily note for that date
note <name>          today's note "<name>"   (YYYY-MM-DD-<name>.md)
note ls              list notes, newest first
note path            print notes directory
```

## Picker

- Type to filter (fuzzy). `Enter` opens the selected note.
- No match? The last row offers `Create new: YYYY-MM-DD-<query>.md`.
- Calendar on top: days with notes are highlighted, today has a background.
- `PgUp` / `PgDn` (or `Ctrl-←` / `Ctrl-→`) move the calendar by a month and filter the list to it. `Ctrl-U` clears the filter.
- `Ctrl-T` opens today's daily note directly.
- `Ctrl-R` renames the selected note (date prefix is kept).
- `Ctrl-D` marks notes, `Enter` moves them to trash (`gio trash`) after typing `yes`.
- `Esc` quits.

## Install

Requires Ruby 3.x.

```
git clone git@github.com:clynderl/note.git ~/Documents/projects/note
ln -s ~/Documents/projects/note/bin/note ~/.local/bin/note
```

## Configuration

| Variable          | Default   | Meaning                       |
|-------------------|-----------|-------------------------------|
| `NOTE_PATH`       | `~/notes` | Where notes are stored        |
| `VISUAL`/`EDITOR` | `nvim`    | Editor used to open a note    |

The daily template lives in `NoteFiles.template` in `bin/note`.

## Credits

`lib/tui.rb` and `lib/fuzzy.rb` are copied from [tobi/try](https://github.com/tobi/try) (MIT). See `LICENSE`.
