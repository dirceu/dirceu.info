---
layout: post
title: GSoC report - week 8
date: 2008-07-18
---

I've been working on the task I described on my last post, about parallelizing request to multiple backends. After many time getting strange errors on the tests I got to isolate the problem - my code wasn't handling the exceptions right.

ZEORaid considers ZODB.POSException.POSError and transaction.interfaces.TransactionError valid answers from storages, as they don't indicate storage failure. The problem was that I was getting some ConflictErrors (a kind of TransactionError) that were being considered a sign of storage failure when running ZODB tests.

Christian helped me to work on hadling this and now all tests are passing. I'm just refactoring the code now and will procceed to the next task: allow defining/removing new backend storages while running using the client tool or reloading the config.
