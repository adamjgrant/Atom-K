Basic Usage
===========

As the name implies, Email meta is a meta tag belonging to the ``head`` tag of an email's ``html``document.

    <!DOCTYPE HTML>
    <html>
      <head>
        <meta name="email-periodical" content="name: 'TimeOut New York';">
        <meta name="email-meta-version" content="0.9.0">
      </head>
      <body>
        ...
      </body>
    </html>

Two attributes are needed for an email meta tag, in conjunction with W3C standards: ``name`` and ``content``.

- ``name``
  - Should start with ``email-`` and the type of email it is (below)
  - To optionally declare a version, use ``email-meta-version``
- ``content``
  - JSON-formatted list of properties for the email meta type.
  - For ``email-meta-version``, the major and minor numbers should be used
    - e.g. if the latest version is 2.3.5, the version would be 2.3 (The highest patch number will always be assumed).

Email Types
===========

- Any undeclared email type is assumed to be of the type ``message``.
- ``periodical``
  - For newsletters, time-based alerts, offers, etc.
- ``handshake``
  - For verifying the email account
- ``notification``
  - Short, read-only messages
- ``storage``
  - Emails with attachments meant for being stored for personal use.
  - Validated only if the sender is equal to the sendee (3rd party programs can add additional customizations).

Properties
==========

Periodical
----------

- name (required)
  - Not just the name of the periodical but the keyword used to uniquely identify (useful for keeping in groups...say you want a Newstand-like app)
- unsubscribe* (required)
  - URL where the client can send a POST request to unsubscribe
- subscribe
  - URL where client can (re)subscribe via a POST request
- description
  - As the name implies, a description of the periodical

* For ``success`` or ``error`` on POST request, the fields ``message-success`` or ``message-error`` should be sent back.
e.g. Success: "We're sorry to see you go, be sure to stop in one of our local stores soon."
e.g. Error: "Sorry, we couldn't find a subscription associated with that email account."

Handshake
---------

- description (required)
  - Message to show in notification of handshake request.
- url* (required)
  - Address to send confirmation.
- name
  - Name of site.
- confirm-redirect
  - If present, takes the user to a url.

* For ``success`` or ``error``, the fields ``handshake-success`` or ``handshake-error`` should be sent back.
e.g. Success: "Your account has been successfully confirmed."
e.g. Error: "We're sorry, something went wrong with your account confirmation."

Notification
------------

- text (required)
  - Body text of notification.
- title
  - Optional title, in case client uses it.

Storage
-------

No properties yet. Settings for storage location should be set for the email provider itself.