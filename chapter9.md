# Regular Expressions

* Slashes followed by a character that doesn't form together a special-character, will, unlike ruby, be preserved:
  ```
  # Ruby: 
  /te\\pt/.match "te\\pt"
  # warning: invalid Unicode Property \p: /te\pt/
  # => nil

  // JS:
  /te\pt/.test("te\\pt")
  // => true
  /te\pt/.test("tept")
  // => true
  ```
  Inconvicible!
  
* String''s indexOf cannot take RegExp.
* Question mark: Do not confuse Bash''s wildcard with Regexp''s optional
* How to make /.*/ match multilines? Oh my: use /[^]*/ rather than /.*/  (would it have worked in ruby?).
* RegExp.prototype#exec returns false rather than null when no match was found.
* The MatchData JS analogue is an array of the following form:
  ```
  [ <Whole match> [, match_for_group1, match_for_group2...],
    { index: <match start position> },
    <The entire string>
  ]
  ```
* When a group ends up not being matched, it''ll undefined will take its place in RegExp.prototype#exec return value (nill in ruby).
* Only the last match of a group that matched multiple times (as in `/.*/`) will appear in this array (same goes in ruby).

## Date
  * Date expects zero based months and 1 based days.
  * Time values are not mandatory in Date and end up being 0 if not given.
  * Date.prototype#getTime returns milliseconds since unix epoch time.

* Unlike Ruby, the ^ and $ anchors are for the beginning and end of a string, not line!
* Backtracking explanation is awesome!
* Go through the poorly written binary regexp exapmle again.

## The replace method
  * $1..$n refers to the matches
  * $& refers to the entire match (like in Ruby!)
  * There''s no replaceAll in JS, the 'g' regexp option does that.
  * Just a reminder: String#prototype.slice expects a start and an a length params.
  * Replace can take a function as the second argument; Its params are: first the whole-match followed by the matched-groups.

## Greed
  * Can backtracking occurr when not using greedy operators?

## Dynamically creating RegExp objects
  * It''s safe to backslash any non-word, non-whitespace character.
  * Why isn''t it safe to backslash a whitespace (new Regexp("\ "))? I mean, it''s stupid to do so, but is there any special meaning to that?
  * String.prototype#search can take RegExpt but unlike indexOF, it cannot take a start position.

## The lastIndex property
  * A RegExpt object''s lastIndex property determines where to start the search in a _input string''s_. lastIndex is taken into account iff in RegExph#prototype.exec and only if the 'g' option is used.
  * lastIndex gets automatically updated by RegExpt.prototype#exec and can easily cause bugs when running the pattern on multiple strings.
  * String.prototype#match return an object of the same structure as RegExp''s exec method, _unless_, a global expression was used, then, a list (array) of matches is returned.

## Parsing an INI file
  * string.split can take regexp.
  * The historical meaning of \r\n

* Like Ruby, JS \w includes underscore
