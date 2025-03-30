---
layout: post
title: GSoC report - week 4
date: 2008-06-22
---

I had some problems this week (many exams and things to do on university), so this was a slow week on GSoC.

I worked on creating tests for my last week's patches. Unfortunately I took the wrong direction, writing some code to monkeypatch the gocept.zeoraid.storage.RAIDStorage.__apply_single_storage() method to provide logging and see if the requests are being distributed; Christian later suggested that it should be better to write a simple storage implementation to avoid using monkeypatching (it doesn't need to be a ClientStorage compatible storage, it just need to implement some needed methods such as gocept.zeoraid.tests.failingstorage.FailingStorage does).

Next week I will work on finishing this task and hopefully starting my next task - parallelize requests to multiple backends, probably.
