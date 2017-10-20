# Mobile apps

IMPORTANT: end-to-end testing (possibly implemented in node).

We need a way to coordinate the testing. Having a way to decide to have everything tested in one way prior and after a release.

Which channels to coordinate the testing of new mobile app features?

* Create dedicated channel on slack for this

* Perhaps share this also on mailing lists (in this email, encourage people to join the slack channel to report on bugs etc.)

* For iOS we can even have a Google form

User navigation of mobile apps ===> We can do a "hackathon" for that here.

Ensure mobile apps and desktop apps have feature parity.

Write some EPICS on github on what we want to do.

## Planned upcoming features:

* Renaming to OONI Probe and changing the UI (likely switching to tabs, grouping tests together, etc.).

* Integrate the IM tests in the mobile app for the next release (e.g. WhatsApp and Facebook Messenger tests).

* Orchestrate silent push notifications (sending some tasks).

* Users can choose which categories they want to test. But instead of testing all URLs in those categories, they only test the URLs that we prioritise on (because they have been found to be blocked in the past).

Replace menu with tabs (similarly to WhatsApp and other apps)

## Architecture for revamping of apps

HOME

* Run tests

* Dashboard (to view results, etc.)

* Don't include names of tests (e.g. Web Connectivity), but rather actions (e.g. test websites).

* Prevent users from running tests concurrently -- show them some animated octopus doing something (like an octopus exploring the ocean and coming across various sea creatures) -- advantage of this lock-in view: It allows us to seaminglessly transition to the results (without expecting users to click on it from the menu)

* Add a page that allows the user to share the measurement or testing with others (similar to OONI Run)

* Add ability to re-test URLs (in the result page).





