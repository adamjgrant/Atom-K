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
        url: 'http://lab95.com/confirm/SX29Sfd948dfjWss301LK'
      "
    >
    <!-- Optional -->
    <meta name="email-meta-version" content="0.9.0">
    
With a simple <meta> tag denoting the type of email, email programs can sort by this universal protocol. 
Read-only messages can be put in little dialogue boxes. Periodicals can be grouped into newsstand organizers. 
It's really up to the email client.
