Basic Usage
===========

As the name implies, Email meta is a meta tag belonging to the ``head`` tag of an email's ``html``document.

    <!DOCTYPE HTML>
    <html>
      <head>
        <meta name="email-periodical" content="name: 'TimeOut New York';">
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
