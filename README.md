# week7-wp

# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability Name or ID<br>
[!] Title: Twenty Fifteen Theme <= 1.1 - DOM Cross-Site Scripting (XSS)<br>
    Reference: https://wpvulndb.com/vulnerabilities/7965<br>
    Reference: https://blog.sucuri.net/2015/05/jetpack-and-twentyfifteen-vulnerable-to-dom-based-xss-millions-of-wordpress-websites-affected-millions-of-wordpress-websites-affected.html<br>
    Reference: http://packetstormsecurity.com/files/131802/<br>
    Reference: http://seclists.org/fulldisclosure/2015/May/41<br>
    Reference: https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-3429<br>
[i] Fixed in: 1.2<br>
<br>
  - [x] Summary: Twenty Fifteen Theme <= 1.1 - DOM Cross-Site Scripting (XSS)
    - Vulnerability types: DOM XSS
    - Tested in version: 4.2
    - Fixed in version: ?
  - [x] GIF Walkthrough: ![](https://github.com/alfasin/week7-wp/blob/master/CVE1.gif)
  - [x] Steps to recreate: simply go to: `http://wpdistillery.vm/wp-content/themes/twentyfifteen/genericons/example.html#1<img/ src=1 onerror= alert(1)>`
  - [x] Affected source code:
    - [Link 1](https://github.com/Automattic/Genericons/commit/798ac98579dd72dfdb11bdee3e7bebf01cffb1f7)
    
2. (Required) Vulnerability Name or ID
[!] Title: WordPress  4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
    Reference: https://wpvulndb.com/vulnerabilities/8768
    Reference: https://wordpress.org/news/2017/03/wordpress-4-7-3-security-and-maintenance-release/
    Reference: https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8
    Reference: https://blog.sucuri.net/2017/03/stored-xss-in-wordpress-core.html
    Reference: https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-6817
[i] Fixed in: 4.2.13

  - [x] Summary: Stored XSS using encoded links in the Post body
    - Vulnerability types: Stored XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.3
  - [x] GIF Walkthrough: ![](https://github.com/alfasin/week7-wp/blob/master/CVE2.gif)
  - [x] Steps to recreate: edit a post, use the 'text' tab (not visual!) and add the following string: `[embed src='https://www.youtube.com/embed/U2lZIUZ_ZwU\x3csvg onload=alert(1)\x3e'][/embed]` then go to the post-page
  - [x] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
    
3. (Required) Vulnerability Name or ID
[!] Title: WordPress 3.6.0-4.7.2 - Authenticated Cross-Site Scripting (XSS) via Media File Metadata
    Reference: https://wpvulndb.com/vulnerabilities/8765
    Reference: https://wordpress.org/news/2017/03/wordpress-4-7-3-security-and-maintenance-release/
    Reference: https://github.com/WordPress/WordPress/commit/28f838ca3ee205b6f39cd2bf23eb4e5f52796bd7
    Reference: https://sumofpwn.nl/advisory/2016/wordpress_audio_playlist_functionality_is_affected_by_cross_site_scripting.html
    Reference: http://seclists.org/oss-sec/2017/q1/563
    Reference: https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-6814
[i] Fixed in: 4.2.13

  - [x] Summary: stored xss using media-file metadata and audio playlist
    - Vulnerability types: stored xss
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: ![](https://github.com/alfasin/week7-wp/blob/master/CVE3.gif)
  - [x] Steps to recreate: 
        - upload [xss.mp3](https://github.com/alfasin/week7-wp/blob/master/xss.mp3) to the media tab
        - go to the post and click on "add media
        - click on the option of "create audio playlist"
  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/28f838ca3ee205b6f39cd2bf23eb4e5f52796bd7)
    
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
