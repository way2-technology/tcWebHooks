

# tcWebHooks - A TeamCity plugin to send webhooks for build events

[![Join the chat at https://gitter.im/way2-technology/tcWebHooks](https://badges.gitter.im/way2-technology/tcWebHooks.svg)](https://gitter.im/way2-technology/tcWebHooks?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![status](https://teamcity.jetbrains.com/app/rest/builds/buildType:WebHooksAndOtherPlugins_TcWebHooks/statusIcon)](https://teamcity.jetbrains.com/viewType.html?buildTypeId=WebHooksAndOtherPlugins_TcWebHooks&guest=1)
[![license](https://img.shields.io/badge/license-MIT%20License-blue.svg?style=flat)](https://opensource.org/licenses/MIT)

tcWebHooks is a TeamCity plugin which sends webhook HTTP POST requests to a destination of your choice.
WebHook POSTs for events are a great way to use an event driven architecture to get updates in other systems, rather than polling teamcity for build state changes.  

Typical use cases include:
- Posting messages to chat systems
- Informing systems of events that should trigger an action. eg, deployment, packaging, etc
- Controlling hardware like a lava lamp, build bunny, etc.
- Anything else that would like to know about an event, rather than having to poll.

## Features

### Standard features
- WebUI for [creating webhooks](https://github.com/way2-technology/tcWebHooks/wiki/Creating-a-WebHook "Creating a WebHook") 
- A customizable webhook body via various different means (templates, build properties, custom parameters)
- Can be triggered from many different events in the build lifecycle
- [WebHook Templates](https://github.com/way2-technology/tcWebHooks/wiki/WebHook-Templates-:-An-Introduction), for specification of a payload format once and re-use across multiple webhook configurations
- A set of templates for common services. Eg, Slack and MatterMost, Flowdock, ElasticSearch
- A standard list of [variables](https://github.com/way2-technology/tcWebHooks/wiki/Example-Webhook-output "Example Webhook output") which can be used for assembling a custom payload (eg, `${buildStatusUrl}`), as well as access to the TeamCity build properties (eg, `${teamcity.agent.jvm.os.name}`).
- Basic Auth and Bearer Token [Authentication](https://github.com/way2-technology/tcWebHooks/wiki/Enabling-Authentication) 

### Advanced Features
- Support for [using a proxy](https://github.com/way2-technology/tcWebHooks/wiki/Using-a-proxy-server "Using a proxy server")  for outbound requests.
- Regular Expression [Filter support](https://github.com/way2-technology/tcWebHooks/wiki/Applying-Filtering-Criteria-To-WebHook-Execution "Applying Filtering Criteria To WebHook Execution") , which allows conditionally controlling an event based on text in the webhook properties 
- A [REST API](https://github.com/way2-technology/tcWebHooks/wiki/WebHooks-REST-API "WebHooks REST API")  for creating/modifying webhook templates (with a plan to support creating/editing webhooks in the future)
- [Custom Headers](https://github.com/way2-technology/tcWebHooks/wiki/Custom-Headers) for when your endpoint just expects something specific in a header
- Import and export of webhook templates for sharing via REST API
- Control of [HTTP timeouts](https://github.com/way2-technology/tcWebHooks/wiki/Adjusting-HTTP-timeouts-on-a-webhook "Adjusting HTTP timeouts on a webhook") 

## Requesting Help
The wiki is a good first point of call for help with getting started, and configuring tcWebHooks. If you find a bug or believe there is a missing feature, please create an issue on Github. For questions and discussions, there is also a Gitter chat setup. Please bear in mind that I also have a full time job, a wife and kids, and am probably not in your timezone. Hopefully over time we'll build up a group of people that can help if I'm not online.

Documentation | Bug and Feature Requests | Chat/Discussion
------------- | ------------------------ | ---------------
[tcWebHooks Wiki](https://github.com/way2-technology/tcWebHooks/wiki)  | [tcWebHooks Issues](https://github.com/way2-technology/tcWebHooks/issues)  |  [tcWebHooks on Gitter](https://gitter.im/way2-technology/tcWebHooks)

## Screenshots
#### WebHook Creation/Editing screen
![Screenshot showing the "Add New WebHook" screen](https://raw.githubusercontent.com/way2-technology/tcWebHooks/master/docs/images/Screenshot_AddWebHook_04_ConfigureUrlFormatAndEvents.png "Add New WebHook") 

#### WebHook Template Payload Editing screen
![Screenshot showing the "Edit Build Event Template" screen](https://raw.githubusercontent.com/way2-technology/tcWebHooks/master/docs/images/Screenshot_Templates_EditBuildEventTemplate.png "Edit Build Event Template") 

#### Error logging screen in Admin Tab
![Screenshot showing the "WebHooks Admin tab"](https://raw.githubusercontent.com/way2-technology/tcWebHooks/master/docs/images/Screenshot_AdminTab_StatsAndErrors.png "WebHooks Admin Tab in TeamCity administration section") 
