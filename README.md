# Project 7 - WordPress Pentesting

Time spent: 8 hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress.

## Pentesting Report

### 1. Legacy Theme Preview Cross-Site Scripting (XSS) - CVE-2015-5733
  - [ ] Summary: 
    - Vulnerability types: Persistent Cross-Site Scripting
    - Tested in version: 4.2
    - Fixed in version: 4.2.4
  - [ ] GIF Walkthrough: 
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
      -    Any user that vists this WordPress site and clicks on the Widget link, will see an alert box appear with a 200 on the screen. The Widget is part of the sidebar navigation menu so it will appear no matter which post or page the user is viewing.
  - [ ] Affected source code:
    - [Link 1: WordPress Core Changes](https://core.trac.wordpress.org/changeset/33529)
  
### 3. (Required) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version: 4.2
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

## Assets

List any additional assets, such as scripts or files.

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/) 
- https://wpscan.com/vulnerability/7d99fa14-0b94-4e9a-9fc0-d3f22648be4e
- https://blog.sucuri.net/2015/08/persistent-xss-vulnerability-in-wordpress-explained.html
- https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5734
- https://wpscan.com/vulnerability/32787617-081f-4743-a9a7-5dd6642308b2
- https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5732

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
