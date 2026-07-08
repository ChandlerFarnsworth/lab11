# Assignment #11 – Discussion Report

**Form URL:** _[paste the live URL of your uploaded form here]_

Adding proper semantic structure made the biggest difference in usability and accessibility for this form. Marking up the page title as an `<h1>`, giving the page a descriptive `<title>`, and wrapping each related group of fields in `<fieldset>`/`<legend>` elements turned what was previously a flat wall of text into something a screen reader can navigate meaningfully. Before these changes, tabbing through the form announced almost nothing about what each field was for; now the "Speaker Info" and "Type of Presentation" legends are read aloud as the user enters each group, so they always know which section they are in. The most important change was explicitly associating every `<label>` with its input using the `for`/`id` pairing. This means a screen reader speaks the field's name as soon as focus lands on it, and it also enlarges the clickable target—clicking the label text now selects the radio button or moves focus into the text field, which helps people with motor impairments who struggle with small targets.

The styling changes reinforced these structural improvements and added visual accessibility. Setting the labels to `inline-block` with a fixed width and right alignment lined the fields up cleanly so the form is easier to scan, while removing the list bullets reduced visual clutter. Highlighting the current keyboard/mouse focus with a high-contrast color (white text on a dark red background) gives sighted keyboard users clear feedback about where they are on the page—something the original inaccessible version completely lacked. Finally, cueing required fields with both an asterisk and a yellow background follows the principle of never relying on color alone: users who cannot perceive the color still get the asterisk, and users who might miss the asterisk still get the color, plus a short instruction line at the top explains the convention. Together these techniques benefit a wide range of users: blind users relying on a screen reader, low-vision and colorblind users who need contrast and redundant cues, and keyboard-only or motor-impaired users who depend on visible focus and large click targets.

---

## What was changed in the files (for your reference)

**form-exercise1(one).html**
- Changed `<p>2020 Proposal Form</p>` to `<h1>` for a proper page heading.
- Rewrote the `<title>` from "Forms" to a descriptive title.
- Wrapped "Speaker Info" and "Type of Presentation" in `<fieldset>` with `<legend>`.
- Replaced every `<span>` field name with a `<label for="…">` tied to the input's `id` (all 6 text fields + both radio buttons).
- Added an instructions paragraph explaining required-field convention.
- Added asterisk markers on the three required fields (First Name, Last Name, Address).
- Kept `lang="en"` on the html element.

**css/form.css**
- Added `label` styling: `inline-block`, fixed width, right alignment.
- Removed bullets with `#formcol1 li { list-style:none; }`.
- Pulled the radio choices closer together and left-aligned their labels.
- Added focus/active highlighting rule (white on dark red).
- Added `#formcol1 input.reqfield { background:#FF9; }` to color required fields.
