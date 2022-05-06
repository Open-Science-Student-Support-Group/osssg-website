---
title: Event title
subtitle: A one sentence description of the event.
date: 1999/01/24
categories:
- talks
- workshops
- hangouts
- etc

event:
  speaker: The event speaker(s)
  date: Month 1, 1999
  start: 4:00 PM
  end: 5:30 PM
  location: University of Calgary
  registration_link: https://github.com
---

<!--
This is a comment; it will not appear in the rendered post.

You can modify any of the text below; this is just a template to get you started. For example, if there isn't a speaker you could remove the speaker line, or if there are multiple speakers you could make it plural.

The shortcodes below reference the values you input under the `event` parameter in the post's YAML above. For example {{< meta event.speaker >}} references `event: speaker: The event speaker(s)`.
-->

## Event Details

| __Speaker__: {{< meta event.speaker >}}
| __Date and Time__: {{< meta event.date >}}, from {{< meta event.start >}} to {{< meta event.end >}}
| __Location__: {{< meta event.location >}}

A detailed event description.

<!--
This is a registration button for the event. The URL for the button can be specified in the `registration_link` YAML parameter above. If you don't need a registration button you can remove the shortcode below.
-->
{{< include ../../../_common/event-registration-button.md >}}
