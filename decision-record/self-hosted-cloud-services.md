# Decision Record: Using self-hosted services for Rejekts conference organisation

**Status:** Pending

## Context

Organising Cloud Native Rejekts conferences requires several collaborative tools for file storage, communication and coordination across different teams. Currently, we rely on various fragmented third-party services (mostly Google Suite), which hasn't been the most streamlined to work with. As we aim to have more conferences being organisers in the future we need a way to better manage access and organisation that meets our needs. We have seen issues especially with communication, both internally between the organisers and with external parties.

## Decision

We have decided to transition to self-hosted infrastructure for the core organisational services of Cloud Native Rejekts. This approach will centralise our operations and provide more control over our data and tools. As a secondary goal, this will also avoid the need for organising members to have a Google account to participate in organising (although we will still have a requirement on GitHub).

The following services will be implemented:

* **File Storage and Shared Calendar:** Nextcloud will serve as our primary platform for document storage and shared event scheduling. This replaces the need for Google Drive and also provides a calendar that can be subscribed to by any client, not just Google Calendar.
* **Shared Inbox:** We will implement a shared inbox tool to manage communications with external parties so that multiple people can access the inbox and history. We want to stop any use of personal email for communication. (Specific tool to be decided).
* **Chat Platform:** Rocket.Chat will be used as our chat platform. It provides text, voice and video capabilities so should be suitable for all organiser communication.
* **Authentication:** Access to these services will be managed via an authentication provider powered by GitHub organisation teams. Each event will have a new GitHub team created that can be used for access control. Extra teams can also be setup for specific purposes when extra permissions are needed. (Specific tool to be decided, likely Dex if it meets all requirements)

## Consequences

* **Pros:**

  * Centralised and unified set of tools for all organisers.
  * Reduced reliance on varied third-party subscription models.
  * Ability to customise tools to specific conference needs.
  * Avoid the need for organisers to use any of their personal accounts for organising activities.

* **Cons/Risks:**

  * Requires ongoing maintenance and operational overhead.
  * Requires dedicated infrastructure and hosting resources.
  * Responsibility for backups, security patches, and uptime falls on the Steering Committee.

## Funding Model

This transition and the ongoing maintenance of these services will be made possible through the introduction of a new **Continuity tier sponsorship**. This tier will be specifically designed for companies who wish to offer year-round support for running and maintaining our self-hosted services and similar costs not tied to a specific conference.
