# Notes on [<q>How to Make a Digital Talking Book</q>](https://lccn.loc.gov/2021689457)

The process is based on NLS NG04:2013 (Draft) which itself is based on NLS NG01:2014.  The scope is confined to digital talking books, but aspects of the workflow will apply to digital talking magazines.

## Setup
1. Enter Metadata
Session Property Window ("File" &rarr; "Properties&hellip;").  Pay attention to the base file name.

## Recording
1. Setting proper signal levels 
Refer to Appendix 1 of NLS NG04 (6.6.1?) re RMS levels.

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

---

# Observations
* Consider producing an <tt>.opf</tt> template
* Items apparent in video include:
	* Ubuntu 10.04.3-desktop-i386.iso<br />Noteworthy since Gutenberg DTB duplication system ("toaster") source code refers to Fedora 14 specifically.
	* sonic-visualizer-2.2.msi<br />Windows Subsystem for Linux with a copy of [sox](https://sox.sourceforge.net/) installed suffices:<br /><code>sox -S "${i}" -n spectrogram  -X $(soxi -D "${i}") -Y $(($(soxi -r "${i}") / 100)) -z $(echo "$(soxi -c "${i}")&#x2a;20&#x2a;(l(2^$(soxi -b "${i}"))/l(10))" | bc -l | tr "." "\n" | head -n 1)  -m  -t "${i}"  -c "$(soxi -r "${i}") Hz, $(soxi -b "${i}") bits, $(soxi -c "${i}") channel$(if [ $(soxi -c "${i}") -gt 1 ] ; then printf "s";fi); $(soxi -d "${i}")" -o "${i}.png"</code> where <code>$<var>i</var></code> holds the current file name.  (Tack on <code>&& optipng -o7 -zm1-9 "${i}.png" ;</code> to make it <q>Just Right&tm;</q>.)
  * 7z920.msi<br />Presumeably for PDTBs; Windows Subsystem for Linux with GNU zip suffices.
  * DTBCwriteProtect-1.3.0a.msi<br />Windows only, from NLS only.  Reference on screen to Java 7 runtime environment.
  * HindenburgABC-NLS(1.06.1900-1).msi<br />[Hindy](https://hindenburg.com/products/hindenburg-abc-nls) FtW.
