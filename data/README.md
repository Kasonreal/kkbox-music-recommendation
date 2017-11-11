- `raw/*.csv`, `raw/7z/*.7z`: unziped & zipped raw data
- `labeled_train_X`: labelized training data ->` train` left join `songs` left join `members`
  - Note: Unable to perfectly match`artist_name`, `composer` and `lyricist` yet. `光良 (Michael Wong)` and `光良` should be the same guy but currently they would have different labels.
- `train_y`: corresponding `target` value for `labeled_train_X`
- `labeled_test_X`: labelized testing data

