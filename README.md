# Project 7 - WordPress Pentesting

Time spent: 5 hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Stored XSS
  - [X] Summary: 
    - Vulnerability types:XSS
    - Tested in version:4.2
    - Fixed in version: 4.4
  - [X] GIF Walkthrough: [Here](WPExploit1.gif)
  - [X] Steps to recreate: 
      1.use a script when typing in a User Comment
    ```javascript
    <script>alert('XSScommentattack')</script>
    ```
  - [X] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
    - [Vulnerability DB](https://wpvulndb.com/vulnerabilities/8358)
2. (Required) XSS Vulnerability
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version:4.2
    - Fixed in version:4.4
  - [X] GIF Walkthrough: [Here](WPExploit2.gif)
  - [X] Steps to recreate:
    -Change the title of a post to a XSS attack such as
    ```javascript
    <script>alert('POSTXSSAttack')</script>
    ```
  - [X] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
    - [Link 2](http://wpdistillery.local/)
3. (Required) XSS on adding new media
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.6
  - [X] GIF Walkthrough: 
  - [X] Steps to recreate:[Here](WPExploit3.gif)
     1. add media file and in description put in a script
     ```javascript
     <img src="1" onerror=alert('PictureXSS')>
     ```
     that script wil run on the page load of the attachment
     
  - [X] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
    - [Link 2](http://wpdistillery.local/?attachment_id=11)
4. Username Login Enumeration
  - [X] Summary: 
    - Vulnerability types: Username Enumeration
    - Tested in version: 4.2
    - Fixed in version: 4.7
  - [X] GIF Walkthrough:[Here](UserNameEnumeration.gif)
  - [X] Steps to recreate: 
    - We went into the login page and tried usernames that we did not know existed and it gave us specific explaination why that did not       work since username was invalid. When we tried to login as admin it told us that with a different password that an admin account existed but the password was wring 
  - [X] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

I think the wrose part was getting the Kali and Vagrant to work together to analyze the shortcommings of verion 4.2 of WordPress

## License

    Copyright [2018] [Shaishav Naik]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
