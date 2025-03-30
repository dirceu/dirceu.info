---
layout: post
title: Quick Tip - Testing Django send_mail
date: 2008-10-07
---

I've been working on a Django project lately and I had the need to send some emails from my application. I was trying to figure out how to write a mocked version of django.core.mail.send_mail when I read about <a title="Django - Testing Email Services" href="http://docs.djangoproject.com/en/dev/topics/testing/#e-mail-services">django.core.mail.outbox</a>, which apparently is a new feature of Django 1.0.

django.core.mail.outbox is a list of all instances of emails sent with django.core.mail.send_mail that is available only in the testing framework. With it you can do things like these:

<script src="http://gist.github.com/15413.js"></script>
(<a title="gist 15413" href="http://gist.github.com/15413">Link of the Gist</a>)