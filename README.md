# week7-wp

# Project 7 - WordPress Pentesting

Time spent: **5** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability Name or ID: Twenty Fifteen Theme <= 1.1 - DOM Cross-Site Scripting (XSS)

  - [x] Summary: Twenty Fifteen Theme <= 1.1 - DOM Cross-Site Scripting (XSS)
    - Vulnerability types: DOM XSS
    - Tested in version: 4.2 + Twenty Fifteen Theme <= 1.1
    - Fixed in version: Twenty Fifteen Theme >= 1.2
  - [x] GIF Walkthrough: ![](https://github.com/alfasin/week7-wp/blob/master/CVE1.gif)
  - [x] Steps to recreate: simply go to: `http://wpdistillery.vm/wp-content/themes/twentyfifteen/genericons/example.html#1<img/ src=1 onerror= alert(1)>`
  - [x] Affected source code:
    - [Link 1](https://github.com/Automattic/Genericons/commit/798ac98579dd72dfdb11bdee3e7bebf01cffb1f7)
    
2. (Required) Vulnerability Name or ID: WordPress  4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds

  - [x] Summary: Stored XSS using encoded links in the Post body
    - Vulnerability types: Stored XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.3
  - [x] GIF Walkthrough: ![](https://github.com/alfasin/week7-wp/blob/master/CVE2.gif)
  - [x] Steps to recreate: 
    + edit a post 
    + use the 'text' tab (not visual!) 
    + add the following string: `[embed src='https://www.youtube.com/embed/U2lZIUZ_ZwU\x3csvg onload=alert(1)\x3e'][/embed]`
    + go to the post-page
    
  - [x] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
    
3. (Required) Vulnerability Name or ID: WordPress 3.6.0-4.7.2 - Authenticated Cross-Site Scripting (XSS) via Media File Metadata

  - [x] Summary: stored xss using media-file metadata and audio playlist
    - Vulnerability types: stored xss
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: ![](https://github.com/alfasin/week7-wp/blob/master/CVE3.gif)
  - [x] Steps to recreate: 
        + upload [xss.mp3](https://github.com/alfasin/week7-wp/blob/master/xss.mp3) to the media tab
        + go to the post and click on "add media
        + click on the option of "create audio playlist"
        
  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/28f838ca3ee205b6f39cd2bf23eb4e5f52796bd7)
    
4. (Optional) Vulnerability Name or ID: WordPress 2.5-4.6 - Authenticated Stored Cross-Site Scripting via Image Filename

  - [x] Summary: stored xss using image filename
    - Vulnerability types: stored xss
    - Tested in version: 4.2
    - Fixed in version: 4.2.10
  - [x] GIF Walkthrough: ![](https://github.com/alfasin/week7-wp/blob/master/CVE4.gif)
  - [x] Steps to recreate: 
      + create a file with the following name: `engizhansahinsumofpwn<img src=a onerror=alert(document.cookie)>.jpg`
      + upload it using the "media" tab
      + click the uploaded file
      + click on "View attachment page" link or alternatively go to: http://wpdistillery.vm/?attachment_id=[ID] replace [ID} with the attachment id.<br>
      + you should get an alert pop-up with the cookie
      
  - [x] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/c9e60dab176635d4bfaaf431c0ea891e4726d6e0)
    
    
5. (Optional) Vulnerability Name or ID: WordPress <= 4.2.2 - Authenticated Stored Cross-Site Scripting (XSS)

  - [ ] Summary: Post may contain link with onmouseover event 
    - Vulnerability types: stored xss
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [x] GIF Walkthrough: ![](https://github.com/alfasin/week7-wp/blob/master/CVE5.gif)
  - [x] Steps to recreate: 
      + edit/create a post
      + paste the following content: `<a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>`
      + any user opens the post
      + the user passes the mouse on the link
      + the alert pop-up is triggered      
  - [x] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/changeset/33359) 

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
