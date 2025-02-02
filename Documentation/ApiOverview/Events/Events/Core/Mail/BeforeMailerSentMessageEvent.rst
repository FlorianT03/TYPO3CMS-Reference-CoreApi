..  include:: /Includes.rst.txt
..  index:: Events; BeforeMailerSentMessageEvent
..  _BeforeMailerSentMessageEvent:

============================
BeforeMailerSentMessageEvent
============================

..  versionadded:: 12.0

The PSR-14 event :php:`\TYPO3\CMS\Core\Mail\Event\BeforeMailerSentMessageEvent`
is dispatched before the message is sent by the mailer and can be
used to manipulate the :php:`\Symfony\Component\Mime\RawMessage` and the
:php:`\Symfony\Component\Mailer\Envelope`. Usually a
:php:`\Symfony\Component\Mime\Email` or :php:`\TYPO3\CMS\Core\Mail\FluidEmail`
instance is given as :php:`RawMessage`. Additionally the mailer instance is
given, which depends on the implementation - usually
:php:`\TYPO3\CMS\Core\Mail\Mailer`. It contains the
:php:`\Symfony\Component\Mailer\Transport` object, which can be retrieved using
the :php:`getTransport()` method.

Example
=======

Registration of the event listener in the extension's :file:`Services.yaml`:

..  literalinclude:: _BeforeMailerSentMessageEvent/_Services.yaml
    :language: yaml
    :caption: EXT:my_extension/Configuration/Services.yaml

Read :ref:`how to configure dependency injection in extensions <dependency-injection-in-extensions>`.

The corresponding event listener class:

..  literalinclude:: _BeforeMailerSentMessageEvent/_MyEventListener.php
    :language: php
    :caption: EXT:my_extension/Classes/Mail/EventListener/MyEventListener.php

API
===

..  include:: /CodeSnippets/Events/Core/BeforeMailerSentMessageEvent.rst.txt
