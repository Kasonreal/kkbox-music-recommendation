- `raw/*.csv`, `raw/7z/*.7z`: unziped & zipped raw data
- `labeled_train_X`: labelized training data -> `train` left join `songs` left join `members`
  - Note: Unable to perfectly match`artist_name`, `composer` and `lyricist` yet. `光良 (Michael Wong)` and `光良` should be the same guy but currently they would have different labels
  - Use `re.split('\||\| |,|/', s)` to split multiple artists
  - Use `m = re.compile('(.+) \((.+)\)').match("光良 (Michael Wong)")` to match the `name (alt_name)` pattern, where `m.group(1) == name` and `m.group(2) == alt_name`
  - Problem: How should we map multiple artists to a single label?
- `train_y`: corresponding `target` value for `labeled_train_X`
- `labeled_test_X`: labelized testing data

