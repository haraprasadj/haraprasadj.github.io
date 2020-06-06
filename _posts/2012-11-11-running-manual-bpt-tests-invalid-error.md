---
layout: post
title: Running Manual BPT Tests - Invalid Error Shown By QC
categories: [TechNotes]
---

We use QC 10 and seeing the capability of creating BPT components for manual testing, we quickly
adpated and started creating manual business components and manual tests using these components.
But quickly hit a roadblock when we tried executing these tests.

An error message was displayed on clicking on Run in Test Lab saying, "This version of Quality
Center does not support running components of the type MANUAL. Immediately there were questions
ranging from "When are we moving to QC11?" to "Who did a POC before moving into BPT for manual
testing?".

Only when one team member googled to check this did we realize that the error message itself was
erroneous. What we actually needed to do was - click on the little black down arrow next to the
Run button and from there select, "Run Manually".

Looks like the default Run button for BPT tests is for automated execution. We need to explicitly
instruct QC to run a test manually. I wonder why this is so (although the tester in me says that
it is a defect in QC itself). Since the test uses manual business components, QC should be able to
understand that this requires a manual run. I also wonder if we can have BPT tests which can be executed
both manually and automated. If this is not the case, this segregation of Run options does not make much
sense to me.
