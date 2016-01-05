---
layout: page
title: Registration
---
A `Registration` object describes one school or other organization's entry into a tournament. It comprises the basic details about an organization and one or more [`Team`][team] objects.

It is expected that each `Registration` object represents a distinct school or other organization. For instance, if "Anywhere High School" enters two teams, there should not be two `Registration` objects `name`d `Anywhere A` and `Anywhere B` and one `Team` child each, there should be one `Registration` object `name`d `Anywhere` (or `Anywhere High School`) and two `Team` children.

## Registration object

<table class="fields"><tbody>
  <tr class="required">
    <th>name</th>
    <td class="type">String</td>
    <td>The school or other organization's name.</td>
  </tr>
  <tr class="optional">
    <th>location</th>
    <td class="type">String</td>
    <td>The location of this team's origin. This may be any combination of city, state, country, etc., as appropriate for the tournament, and should be in human-readable format.</td>
  </tr>
  <tr class="required">
    <th>teams</th>
    <td class="type"><nobr>Array <code><a href="{{ site.baseurl }}/team">Team</a></code></nobr></td>
    <td>The teams registered to play for this school or organization.</td>
  </tr>
</tbody></table>

[team]: {{ site.baseurl }}/team
