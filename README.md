# EEM076 2020LP4 Lectures LLC

## Background
When studying for the resit exam, I discovered that the 2020 lecture recordings are still available on Canvas. Since I'll be watching them anyway, I decided to watch them in LosslessCut so I can cut out the unnecessary parts and label the segments for future reference. I thought I might as well share my LLC files on the off chance that someone else out there has access to the videos and needs them.

## Instructions
### Setup
1. Clone/[download](https://github.com/TraumatizedTuna/EEM076-2020LP4-Lectures-LLC/archive/refs/heads/main.zip) the repo.
2. Add [lecture recordings](https://canvas.chalmers.se/courses/9375/modules) to the repo.
3. Open a recording in [LosslessCut](https://github.com/mifi/lossless-cut/releases). It should automatically grab the LLC with the same filename.
4. Play segments using the colorful play button.
<br>!["Play selected segments in order" button from LosslessCut](play_segments.svg)
>[!TIP]
>Not into frying your eyes? Hit `ctrl+shift+i` followed by `esc` to open the console and enter `document.getElementsByTagName("video")[0].style.filter="invert() hue-rotate(180deg)"`.

### Select Segments by [Label](#label-conventions) Content
1. Right click a segment in the sidebar and click `Deselect all segments`.
2. Right click again and `Select segments by expression`.
3. Enter a JS expression to select what you want, for instance:
   * Excercises:<br>`segment.label.includes('[EXC]')`
   * Introductions, summaries and derivations:<br>`['[INT]', '[SUM]', '[DER]'].some(x => segment.label.includes(x))`
   * Questions in excercises (label contains both strings):<br>`['[Q]', '[EXC]'].every(x => segment.label.includes(x))`
   * Anything about Gauss:<br>`segment.label.toLowerCase().includes('gauss')`
>[!TIP]
>Combine conditions using `||` (OR), `&&` (AND) and `!` (NOT).<br>
>(Or use [RegEx](https://regexr.com/) if you're feeling kinky, I suppose.)

### Recommended Export Settings
Set `Export mode` to `Merge cuts` and enable `Create chapters from merged segments`.

I haven't gotten `Smart cut` to work, despite trying a bunch of different settings. If you just want an audio file, however, you can extract the audio track and then cut the extracted file using the same `.llc` file, resulting in a significantly tighter cut.


## Label Conventions
* `[INT]` - Introduction
* `[SUM]` - Summary
* `[EXC]` - Excercise
* `[DER]` - Derivation/explanation (of a formula or law or whatever)
* `[Q]` - Student question
* `[EXT]` - External video
* `+` `-` `?` - Somewhat loosely used to denote that a segment needs to be extended/shortened or should be looked into in general. If combined with other labels, the order indicates which end of the segment needs attention. Dirty? Sure but it's not meant to be permanent anyway.
