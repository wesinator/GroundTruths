# CTI/DFIR truths

CTI and DFIR focused universal truths and technical analysis caveats, in one place.

## Truths

#### Binary Analysis and Triage


| Truth | Reference/Source | 
| ------------- |:-------------:|
| Certain programming frameworks compile executables that will always have the same imphash<br><br>.NET/MSIL: `f34d5f2d4577ed6d9ceec516c1f5a744`, `dae02f32a21e03ce65412f6e56942daa`<br><br>Go/Golang: `f0070935b15a909b9dc00be7997e6112` | https://twitter.com/MalwareRE/status/1207745496451878913 |
| `Armadillo v1.xx - 2.xx` and `v1.71` packer detections, which come from old PEiD signatures, are false positives that actually detect MS VC version headers | https://www.zscaler.com/blogs/research/your-windows-8-packed<br><br>https://github.com/x64dbg/yarasigs/pull/13 |
| VirusTotal's "First Seen in the Wild" date on files (present at the time of writing) seems to be completely arbitrary and does not accurately reflect a particular date of significance with the file. This date field should be ignored as part of analysis using VT data.<br>In general, this is an example of not blindly trusting the full authority of analysis provided by a third party, but vetting everything and applying "common sense" logic. | |
| Microsoft builds many Windows 10 binaries with timestamps that appear in the future. This is done by their build system as a sort of "build hash" to identify related binary builds.<br>Other build systems may do similar things with timestamps. | https://devblogs.microsoft.com/oldnewthing/20180103-00/?p=97705 |
| PE compile timestamp may not be as accurate as the resource section timestamp, depending on the compiler. Some Borland Delphi compilers will set the compile time to always be `0x2A425E19 (708992537)`, `1992-06-19 22:22:17`. | https://www.hexacorn.com/blog/2014/12/05/the-not-so-boring-land-of-borland-executables-part-1/ |
| PE compile timestamps may also reflect the time of the compiler/builder/bundler, for example in the case of archive self-extracting (SFX) executables. For example, certain WinRAR SFX archives always had the compile timestamp `2012-06-09 13:19:49`. | |
