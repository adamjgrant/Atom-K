Atom K
======

A documentation prototype for next generation messaging

Core concepts
-------------

* Interoperability
  * A general messaging interface for messaging systems, not just email. Twitter, facebook, et al. should be optional means for messaging.
  * Backwards compatible with email.
* Messages and calendar events are one in the same.
  * Time has proven that email and calendar need to consistently work together, so why should their particles be different things?
* Supports the sending of HTML5 content.
* Possibility for a commercial standard in addition to open standard, just as Twitter is the commercial standard for tweets.

Syntax
------

Slashes (/) are used for separating a user from the domain, just as email separates with an @.
* john/example.com
* jane.doe/example.com
* alex-miller/example.com

For the commercial standard, user could use extensionless domains
* john/example
* jane.doe/example
* alex-miller/example

Message Types
-------------

<img src="https://s3.amazonaws.com/misc-46578923rb/cluttered-inbox.png"/>

<table>
  <thead>
    <tr>
      <th>Example Subject</th>
      <th>Email Type</th>
      <th>Email Meta Keyword</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>"Hi, Sweetie"</td>
      <td>Message</td>
      <td>None, default</td>
    </tr>
    <tr>
      <td>"Charity News Weekly"</td>
      <td>Periodical</td>
      <td><code>periodical</code></td>
    </tr>
    <tr>
      <td>"Confirm your registration"</td>
      <td>Account-Website Handshake</td>
      <td><code>handshake</code></td>
    </tr>
    <tr>
      <td>"Payment Accepted"</td>
      <td>Read-only notification</td>
      <td><code>notification</code></td>
    </tr>
    <tr>
      <td>"Note to self"</td>
      <td>Personal note, file, or snippet sent to self to be saved or transfered between devices</td>
      <td><code>storage</code></td>
    </tr>
  </tbody>
</table>

How this is solved
------------------

<img src="https://s3.amazonaws.com/misc-46578923rb/handshake.png" />

    <meta 
      name="email-handshake" 
      content="
        description: 'Please confirm your account with Lab95', 
        url: 'http://lab95.com/confirm/SX29Sfd948dfjWss301LK'
      "
    >
    <!-- Optional -->
    <meta name="email-meta-version" content="0.9.0">
    
With a simple <meta> tag denoting the type of email, email programs can sort by this universal protocol. 
Read-only messages can be put in little dialogue boxes. Periodicals can be grouped into newsstand organizers. 
It's really up to the email client.

Why would anyone do this?
-------------------------

- Better for senders
- Better for users
- Backwards compatible
- Unobtrusive
- Pretty cool implications (below)

Greater visibility is a collary of better organization. 
A sender including this meta tag isn't necessary, but would move their message into the user's field of relevance.
And, of course, it's better for the user that emails are put into context. Instead of relying on an email program that
"sniffs" the content of the email to guess a proper category, each message can register itself to the right place.
Because this is valid usage of <a href="http://www.w3.org/wiki/HTML/Elements/meta">HTML meta data</a>, it's unobtrusive and
shows itself only to the discretion of the email client.

Potential User Experience Improvements
--------------------------------------

Here are some ideas for ways email clients could take advantage of the syntax:
<h3><code>periodical</code>s can be set to automatically archive all but the last unread.</h3>
<img src="https://s3.amazonaws.com/misc-46578923rb/latest-unread.PNG" />
<h3>Emailing a photo to oneself could automatically be sent to a companion online storage folder, instead of mixed in with other messages and junk mail.</h3>
<img src="https://s3.amazonaws.com/misc-46578923rb/vacationphotos.png" />
<h3><code>handshake</code> emails could prompt desktop clients to open a UI element such as a Growl message to take the user right to the confirmation page. No need to check the email itself</h3>
<img src="https://s3.amazonaws.com/misc-46578923rb/handshake.png" />
<h3>Different types can be sorted into respective feeds. This means you can read through all your periodicals on the subway, your messages at work, and clear all notifications at once.</h3>
<img src="https://s3.amazonaws.com/misc-46578923rb/tabs.png" />
<h3>Unsubscription to newsletters can be delegated to an actual UI element in the client program. On the same token, being less annoying, users will be less likely to want to unsubscribe.</h3>
<img src="https://s3.amazonaws.com/misc-46578923rb/unsubscribe.png" />

Where to go from here?
----------------------

This is an open source project made for the advancement of humankind.
It's a simple two way street: Email senders can start writing this meta data automatically. Email clients can impress their users with the ability to read these kind of emails.
Just use the syntax in the API document of this repo.

Contributing
------------

This branch is a starting point. Please send pull request to the 1.0 branch
where a stable version of the API is in the works. Senders and sendees can
still use 0.9.0 but should version using ``email-meta-version``. (See API.md)
