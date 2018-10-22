# Project 7 - WordPress Pentesting

Time spent: **3** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Cross Site Scripting for Theme Template Names Version 4.8
  - [ ] Summary: There is a cross site scripting exploitation where template names in certain them files are not sanitized correctly. This allows user input for setting the name to be run and javascript code can be run
    - Vulnerability types: XSS
    - Tested in version: 4.8
    - Fixed in version: 4.8.2
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
    - Go to the “appearance tab” on the dashboard then click on “editor”
    - From there you can edit certain files where they don’t already have template names
    - For example, if you go to the Twenty Fifteen theme and edit author-bio.php with the following script /* Template Name: <script>confirm(document.cookie);</script> */ you can create a popup.

  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/blob/4.8-branch/wp-admin/theme-editor.php)
2. (Required) Cross Site Scripting in Version 4.8 
  - [ ] Summary: When creating a post as an admin, you can input code into the post title and have it execute when previewing the post.
    - Vulnerability types: XSS
    - Tested in version: 4.8
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
      - Go to dashboard
      - Go to add new post
      - Enter code into the post title
      - Click preview post

  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/blob/4.8-branch/wp-admin/post-new.php)
3. (Required) Cross site scripting on post comments in Version 4.8 
  - [ ] Summary: As an admin you can input code into comments of a post which would run the javascript code.
    - Vulnerability types: XSS
    - Tested in version: 4.8
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
    - Go to a post created on the site
     - Add in <img src=1 onerror=alert(document.cookie)> or other code to the input field
    - After posting the comment when the page is refreshed the code executes

  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/blob/4.8-branch/wp-admin/comment.php)

## Assets

List any additional assets, such as scripts or files



## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Some of the challenges experienced during the assignment was trying to get a Github repo when Github was experience database consistency errors. There were also issues with trying to get the right XSS script into the input fields.

## License

    Copyright [2018] 

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
