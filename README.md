# Project 7 - WordPress Pentesting

Time spent: 8+ hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress.

## Pentesting Report

### 1. Legacy Theme Preview Cross-Site Scripting (XSS) - CVE-2015-5734
  - [ ] Summary: 
    - Vulnerability types: Persistent Cross-Site Scripting
    - Tested in version: 4.2
    - Fixed in version: 4.2.4
  - [ ] GIF Walkthrough:
![GIF Not Working](https://github.com/SLyubar/codepath_Unit8/blob/main/exploit1.gif)
  - [ ] Steps to recreate: 
      -    You must be logged in with either an admin or editor role.
      -    Navigate to the comments section of any post.
      -    Post a comment with this payload: <a href='/wp-admin/' title="" style="position:absolute;top:0;left:0;width:100%;height:100%;display:block;"     onmouseover=alert(1)//'>Cats</a>
      -    Once a user scrolls past the "x thoughts on" area of the affected page, an alert box will appear with the number 1 and continously appear as the user navigates the page.
  - [ ] Affected source code:
    - [Link 1: WordPress Core Changes](https://core.trac.wordpress.org/changeset/33549)
   
### 2. Widgets Title Cross-Site Scripting (XSS) - CVE-2015-5732
  - [ ] Summary: 
    - Vulnerability types: Cross-Site Scripting
    - Tested in version: 4.2
    - Fixed in version: 4.2.4
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate:
      -    You must be logged in with either an admin role or trick an admin into creating a new Widget for the navigation menu.
      -    When creating the Widget, the admin needs to post this payload into the body: <a href='/wp-admin/' title="" style="position:absolute;top:0;left:0;width:100%;height:100%;display:block;" onclick=alert(200)//'>Pwned</a>
      -    Ideally, the Widget has a catchy title such as "New Post!"
      -    Any user that vists this WordPress site and clicks on any of the navigation links, will see an alert box appear with a 200 on the screen. The Widget is part of the sidebar navigation menu so it will appear no matter which post or page the user is viewing.
  - [ ] Affected source code:
    - [Link 1: WordPress Core Changes](https://core.trac.wordpress.org/changeset/33529)
  
### 3. Authenticated Stored Cross-Site Scripting (XSS) - CVE-2015-5622/5623
  - [ ] Summary: 
    - Vulnerability types: Cross-Site Scripting
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: 
  ![GIF Not Working](https://github.com/SLyubar/codepath_Unit8/blob/main/exploit3.gif)
  - [ ] Steps to recreate: 
      -    You must be logged in with at least author or contributor status.
      -    When creating a new post, the following payload should be placed into the HTML body (into the text, not the visual tab): <a href="</a><a title=" onmouseover=alert('You have been Pwned!')  ">link</a>
      -    Any user that hovers over the link with their mouse will get an alert message saying "Pwned!"
  - [ ] Affected source code:
    - [Link 1: WordPress Security and Maintenance Update](https://wordpress.org/news/2015/07/wordpress-4-2-3/)

## Assets

List any additional assets, such as scripts or files.

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/) 
- [WordPress Scan Explanation for CVE-2015-5734](https://wpscan.com/vulnerability/7d99fa14-0b94-4e9a-9fc0-d3f22648be4e)
- [Sucuri Blog Explaining CVE-2015-5734 Vulnerability](https://blog.sucuri.net/2015/08/persistent-xss-vulnerability-in-wordpress-explained.html)
- [MITRE Explainion of CVE-2015-5734](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5734)
- [WordPress Scan Explanation for CVE-2015-5732](https://wpscan.com/vulnerability/32787617-081f-4743-a9a7-5dd6642308b2)
- [MITRE Explaination of CVE-2015-5732](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5732)
- [WordPress Scan Explanation for CVE-2015-5622/5623](https://wpscan.com/vulnerability/0f027d7d-674b-4a63-9603-25ea68069c1d)
- [MITRE Explaination of CVE-2015-5622](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5622)
- [MITRE Explaination of CVE-2015-5623](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5623)
- [Twitter Showing a Variation of the Exploit](https://twitter.com/klikkioy/status/624264122570526720)
- [Klikki Post Explaining CVE-2015-5622/5623 Vulnerability](https://klikki.fi/adv/wordpress3.html)

GIFs created with [ScreenToGif](https://www.screentogif.com/).

## Notes

  It was difficult to find vulnerabilities that actually worked in the WordPress environment. Some of them only worked under certain user roles or under specific circumstances.

## License

    Copyright 2022 Stan Lyubarskiy

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
