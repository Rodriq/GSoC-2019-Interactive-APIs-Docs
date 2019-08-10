# Bots Architecture

![Bots Architecture Diagram](./diagram.png){:style="width='100%' height='auto'"}

The above diagram illustrates the general concepts of how a Rocket.Chat server
communicates with a chatbot framework or platform. These concepts are applicable
to [**external**](../) bots.

Bots architecture consists of two main parts: Rocket.Chat host and [bot host](#bots-host).
These two parts are connected with each other via [Rocket Chat SDK](#rocketchat-sdk) methods.
Bot host runs externally to the Rocket.Chat host and consists of SDK, [adapter](#framework-adapter),
[framework](#bot-framework) and, typically, external [services](#external-services).

A bot, being subscribed to room's messages (all or specific ones) handles these
messages and responds back to the user in an interactive manner. The conversational model
can be designed and managed by tooling and frameworks on the bot host.

Today, many bots are created using bot frameworks or platforms based on popular programming
languages, such as NodeJS and Python.

## Users and Bots

Bots in Rocket.Chat require user accounts with the `bot` role. Other than having
a specific set of permissions, bot accounts are treated like regular user accounts
within the Rocket.Chat host. However, to prevent possible user confusion, messages
from online bots are marked with a default "Bot" label.

## Bot Admin

Admins (and only admins) can create the bot account and configure role
permissions. This includes setting the credentials a bot uses to connect
as well as which user fields the bots have access to for privacy and security.
Rocket.Chat team works on improving management views for bots and enhancing
the future potential of user-activated bots.

## Bots Host

A bot host is a machine where bots run. It can be a bare-metal server, a network
cluster, a virtualized environment or cloud-based.

A bot host can manage and run many different bots as well as many instances of any bot.

The bot host typically manages connections to [external services](#external-services)
as well.

## Message Streams

Every user in Rocket.Chat has a collection for their messages that can be
emitted by the server's streamer. Bots subscribe to the collection of messages
for their own user account, creating a stream that is updated every time a
message is sent either directly to them or any room they are joined in.

## Rocket.Chat SDK

The SDK is a low-level software module that offers an interface for external
consumers to subscribe to message streams, send messages, and call methods on the
Rocket.Chat server via WebSockets / DDP.

Bot framework adapter are written using the SDK.

## Framework Adapter

An adapter (also referred as **connector** or **middleware**) is a software component
that is used to link the framework with the Rocket.Chat host.

An adapter allows bot creators to design and build bot interactions according to the
framework's rules and practices without dealing with the low-level programming
details of the communication with the Rocket.Chat host.

Adapters use Rocket.Chat SDK to communicate with the Rocket.Chat host.

## Bot Framework

Bot frameworks (such as Hubot, Botkit, Rasa or Botpress) provide unique
approaches to create conversational interfaces and allow developers
to focus on the design and management of complex bot logic.

Most of framworks can be run on your own bot host. There are also frameworks
that operate as SaaS (Software as a Service), so they work in the cloud.

Most of the popular frameworks have adapters created by the Rocket.Chat's community.

## Bot Scaling

In production, hundreds or thousands of users can be carrying out conversations with a bot
at the same time. The ability to scale a bot from one conversation to many concurrent ones
is essential.

Bot frameworks/platforms support varying degrees of scalability. To ensure that growing number
of users will not cause architectural and performance problems, you should choose your bot's
framework wisely. For example, considerng potential scalability issues even before you start
implementing your bot's logic

## External Services

The value of most production bots relies on their ability to access and manipulate external
data and systems (services). External services, like databases, scheduling systems, CRM, NLP
can be used to provide data or conversational processing.

The framework simplifies connection of a bot with these services and ensures ease of access to
them through the bot host.