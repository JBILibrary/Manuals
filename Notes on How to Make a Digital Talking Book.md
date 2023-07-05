# Notes on [<q>How to Make a Digital Talking Book</q>](https://lccn.loc.gov/2021689457)

The process is based on NLS NG04:2013 (Draft) which itself is based on NLS NG01:2014.  The scope is confined to digital talking books, but aspects of the workflow will apply to digital talking magazines.

## Setup
1. Enter Metadata
Session Property Window ("File" &rarr; "Properties&hellip;").  Pay attention to the base file name.

## Recording
1. Setting proper signal levels 
Refer to Appendix 1 of NLS NG04 (6.6.1?) ABOUT rms LEVELS.

## Markup
Refer to section 7.3 and 7.4 of NLS NG04 to comply with NLS NS01.

The four minimal navigation elements are
1. <tt>docTitle</tt>
1. <tt>docAuthor</tt>
1. <tt>annotation</tt>
1. <tt>closing</tt>

> When marking navigable items, note that the narration of the header is marked, not the full narration of the section.

## Export

## Encryption
NLS Content Protection Software 
> The copyright exemption that permits libraries to create accessible materials requires that the materials are properly protected to prevent them from being played on unauthorized devices and/or used by people who are not eligible for the NLS program.
> A DTB is not complete until it has been protected

# Advanced Tricks and Tips

> Auto-level will adjust every region of the session according to EBU R128, which is within RMS range recommended in NG04.

> Split markers&hellip; should be adjusted so that the side split does not cut off a word or introduce a bad edit.

> Be careful not to cut off a [word or a] breath.
