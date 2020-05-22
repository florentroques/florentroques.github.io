---
permalink: foundation-for-emails-inky-vs-mjml
layout: page
title: "Foundation for Emails (Inky) vs MJML"
date: 2020-05-22
<!--categories: CATEGORY-1 CATEGORY-2-->
---

Email template languages have created significant buzz. They promise to abstract away the quirks and annoyances of email rendering, allowing you to write clean simple code that will be transpiled to raw HTML as a final step. The two leading contenders are Foundation for Emails 2 by Foundation and MJML by MailJet.

Foundation has been providing value to web designers and developers for years. As the leading competitor to Bootstrap, it may seem like the obvious choice for email creation as well. Unfortunately, your past experience with Foundation for websites won't provide much help in the email space. Foundation for Emails creates an entirely new set of tags to learn, which will take some time, but will eventually have you coding emails faster than you thought possible. Foundation for Emails is fully open source and available on GitHub, but your best bet for customization is through building new components. It currently supports 10 components, which covers most typical use cases.

MJML started as an internal project of MailJet. The project grew rapidly and added so much value to the development workflow they decided to release the project on GitHub. MJML quickly gained traction, spreading virally through ProductHunt, Litmus forums, and social channels. The MJML syntax feels simple, making it easy to get up and running. The hardest aspect of using MJML may be learning the command line interface, especially if you are not yet using NPM. Thankfully the MJML team has built multiple support programs, including a desktop editor with live preview.

Jumping into the code, Foundation for Emails and MJML follow similar patters, each has its own tagging syntax:

Foundation for Emails:
```xml
<container></container>
```
MJML:
```xml
<mjml>
    <mj-body>
        <mj-container></mj-container>
    </mj-body>
</mjml>
```
Looking at a blank email, Foundation for Email feels simpler to write, but things become more complicated as we add responsive layouts.

Foundation for Email and MJML both use columns and rows to create grids. Foundation for Email makes use of column attributes large="X" and small="X" to differentiate the width of a column for desktop and mobile views. As you would expect X, represents the number of grid columns to use out of 12. If you tend to create a lot of multi-column mobile layouts this feature becomes very useful.

MJML takes a different approach and assumes that all content will be full-width for mobile devices by default. You can create multi-column layouts by leveraging the tag, but browsing RivalHound's email archive it's hard to find emails that leverage multiple columns on mobile devices. Besides some product suggestions, 99% of mobile emails are one column. Given this trend, MJML's approach seems like a sensible default.

Foundation for Emails:
```xml
<row>
    <columns small="6" large="6">
         <p>Left Column</p>
    </columns>
     <columns small="6" large="6">
        <p>Right Column</p>
    </columns>
</row>
```
MJML:
```xml
<mj-section>
    <mj-group>
        <mj-column>
            <mj-text>Left Column</mj-text>
        </mj-column>
        <mj-column>
            <mj-text>Right Column</mj-text>
        </mj-column>
    </mj-group>
</mj-section>
```
This is a basic example, but it gives you some idea what to expect. MJML syntax is definitely longer, but don't let that be your deciding factor, it feels very natural to write.

As I've used both of these frameworks, it felt as though Foundation for Emails was more designer centric, while MJML appeals to the programmer in me. Both frameworks are capable of making beautiful designs, but MJML seems to push the envelope in features, components, and allowing for graceful degredation across clients instead of making functionality sacrifices for the sake of pixel perfect rendering. This especially comes through with responsive design. MJML appears to be mobile first and begs you to allow the layout to stretch, reorder, or basically respond to the screen size.

In terms of communities and support, Foundation clearly has better name recognition and a larger user base, but the majority of that is focused on website development. MJML's GitHub currently has fewer stars and contributers, but the community is growing rapidly. Issues are responded to and closed extremely quickly and their website and documentation seems very comprehensive.

In a follow-up post I plan to research building custom components for both frameworks. MJML recently announced a new component system so I will wait for it to launch.

I expected Foundation for Emails to win in a landslide given Foundation's history, but I believe MJML has a bright future and if they continue with their current pace may beat out Foundation in features and usability. Currently, this comes down to personal preference. I will be using MJML because of it's willingness to push forward thinking features, mobile-first design, and an excellent focused community. Honestly though, either way you choose, using a framework is the right choice. These tools will drastically improve your productivity and perhaps save you the trouble of hunting down that rendering bug.

source: https://web.archive.org/web/20170616155435/https://www.rivalhound.com/blog/post/inkyvsmjml
