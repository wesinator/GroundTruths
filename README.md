# CTI Ground Truths

Knowledgebase of universal truths, analysis caveats for cyber threat intelligence (CTI) , in one place.

## Truths

#### Binary Analysis and Triage


| Truth | Reference/Source | 
| ------------- |:-------------:|
| Certain programming frameworks compile executables that will always have the same imphash<br><br>.NET/MSIL: `f34d5f2d4577ed6d9ceec516c1f5a744`, `dae02f32a21e03ce65412f6e56942daa`<br><br>Go/Golang: `f0070935b15a909b9dc00be7997e6112` | https://twitter.com/MalwareRE/status/1207745496451878913 |
| Armadillo v1.xx - 2.xx and v1.71 packer detections are garbage false positives that actually detect MS VC version headers | https://www.zscaler.com/blogs/research/your-windows-8-packed<br>https://github.com/x64dbg/yarasigs/pull/13 |
| VirusTotal's "First Seen in the Wild" date on files (present at the time of writing) seems to be completely arbitrary and does not accurately reflect a particular date of significance with the file. This date field should be ignored as part of analysis using VT data.<br>In general, this is an example of not blindly trusting the full authority of analysis provided by a third party, but vetting everything and applying "common sense" logic. | |
| Microsoft builds many Windows 10 binaries with timestamps that appear in the future. This is done by their build system as a sort of "build hash" to identify related binary builds.<br>Other build systems may do similar things with timestamps. | https://devblogs.microsoft.com/oldnewthing/20180103-00/?p=97705 |
