# Project 8 - Pentesting Live Targets

Time spent: **7** hours spent in total

> Objective: Find, analyze, recreate, and document **six vulnerabilities** on a live pentesting site

## Pentesting Report

1. (Required) Vulnerability Name: Username Enumeration (GREEN)
  - [ ] Summary: A careless developer mistake has created a username enumeration vulnerability. 
        Determine which color has the vulnerability. You can use the existing username "jmonroe99" as a test. 
        Next, figure out what mistake the developer made.
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/ImpishEvilLamprey
  - [ ] Steps to recreate: From the three sites; red, blue, green. I noticed green was the only one that didn't bold their
        "Login was unsuccessful." Upon using the inspection tool we can see that in the html "<span class = failed" instead
        of "<span class = failure." 

2. (Required) Vulnerability Name: Insecure Direct Object Reference (RED)
  - [ ] Summary: One of the three sites is missing code which would prevent some sensitive information from being made public. 
        Determine which color has the vulnerability. 
        Then, figure out what the other two sites did correctly to prevent the information leak.
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/ElectricMarriedAdouri
  - [ ] Steps to recreate: The summary gave us a clue about where to search, sensitive information can mean "salesperson."
        There were two salepeople that weren't suppose to be seen in the public site. By checking all three sites and manually 
        changing the url "id" at id=10 for the red site it shows private information.
        
3. (Required) Vulnerability Name: SQL Injection (BLUE)
  - [ ] Summary: Most of the data input received by these websites is being sanitized properly. 
  However, one of the three sites has one place where the input is not being sanitized before being used in an SQL query. 
  Determine which color has the vulnerability.
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/HonestDapperAmericanbobtail
  - [ ] Steps to recreate:SQL injections are usually done on the URL. Knowing that I was trying to inject the statement into public
        "salesperson." On the blue site, upon injecting nothing happens compared to the other sites where you get redirected to the login page.
  
4. (Required) Vulnerability Name: Cross-Site Scripting (GREEN)
  - [ ] Summary: All three sites do a good job of protecting against a reflected XSS attack. 
        However, one of the sites has a mistake which leaves the site vulnerable to a stored XSS attack. 
        A reflected XSS attack would be easy to reveal, while a stored XSS does not provide instant feedback. 
        You will need to log into the admin area and look through the CMS in order to "spring the trap" and find out if your attack succeeded. 
        Determine which color has the vulnerability. Use your name in the XSS so that your results won't be confused with anyone else's (example: <script>alert('Mallory found the XSS!');</script>).
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/GoodCoolAustralianfurseal
  - [ ] Steps to recreate: From previous weeks to recreate an xxs alert I know we can send it through a comment section. So I went 
        to test it on each color. Once we enter the script on the feedback section, which placed a stored XSS attack and when the 
        user checks the feedback page the attack activates.
  
5. (Required) Vulnerability Name: Cross-Site Request Forgery (RED)
  - [ ] Summary: One of the three sites does not have CSRF protections on the admin area. 
  A clever attacker could design a form which would automatically submit form data to the staff area and take advantage of a logged in user's access permissions. 
  Be the attacker and design a form which will make a change to the spelling of some database content. 
  Then point the form action at each of the three sites to find out which color has the vulnerability. 
  Do not neglect to be stealthy with your form—your unsuspecting, logged-in admin should neither see the form nor the results of the form submission.
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/RipeUnequaledAfricanwilddog
  - [ ] Steps to recreate: By creating an html(CSRF.html) that sends a hidden edit to the red site. I was able to secretly change/edit the salesperson.
        Simply open the html and check the red site and you will see the new salesperson.
 
 6. (Required) Vulnerability Name: Session Hijacking/Fixation (BLUE)
  - [ ] Summary: Two of the three websites expire their active sessions and require users to re-login every 30 minutes. 
  That is probably too aggressive for the real world, but it is better than the third site which allows sessions to be a year old, and never regenerates the session ID, even when the user agent string changes. 
  This makes it vulnerable to both session hijacking and session fixation attacks.
  - [ ] GIF Walkthrough: https://gfycat.com/gifs/detail/UnhealthyGleamingEarthworm
  - [ ] Steps to recreate: Using two different browsers and "public/hacktools/change_session_id.php." On chrome copied the generated session id and logged out then on
        safari I got another session id, but by pasted the previous session id that was logged in I was able to access the previous logined in user.

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
