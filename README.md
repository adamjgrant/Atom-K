Email-Meta
==========

A stupidly simple way to make email better, v 0.9.0

<em>Email meta is an open, valid HTML syntax to provide context, structure, and better UX to any conceivable email reader.</em>

Because not all emails are messages.
------------------------------------

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
      <td><code>meta-message</code></td>
    </tr>
  </tbody>
</table>

How this is solved
------------------

    <meta 
      name="email-handshake" 
      content="
        title: 'Lab95.com'; 
        description: 'Confirm your account'; 
        url: 'http://lab95.com/confirm/SX29Sfd948dfjWss301LK';
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

- <code>periodical</code>s can be set to archive all but the last unread.
- Emailing a photo to oneself could automatically be sent to a companion online storage folder, instead of mixed in with other messages and junk mail.
- <code>handshake</code> emails could prompt desktop clients to open a UI element such as a Growl message to take the user right to the confirmation page. No need to check the email itself.
- Different types can be sorted into respective feeds. This means you can read through all your periodicals on the subway, your messages at work, and clear all notifications at once.
- Unsubscription to newsletters can be delegated to an actual UI element in the client program. On the same token, being less annoying, users will be less likely to want to unsubscribe.

How to start this revolution?
-----------------------------

This is an open source project made for the advancement of humankind.
It's a simple two way street: Email senders can start writing this meta data automatically. Email clients can impress their users with the ability to read them.
Just use the syntax crowdsourced and edited in the API document of this repo. It's so easy, why not do it?
