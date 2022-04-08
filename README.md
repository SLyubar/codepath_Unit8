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
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/changeset/33549)
   
### 2. (Required) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version: 4.2
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
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

GIFs created with [ScreenToGif](https://www.screentogif.com/).

## Notes

  It was difficult to find vulnerabilities that actually worked in the WordPress environment. Some of them only worked under certain user roles.

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
