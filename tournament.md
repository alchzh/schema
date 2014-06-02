---
layout: page
title: Tournament
---
A `Tournament` object describes a tournament for which a single result is published. A `Tournament` consists of a number of [`Match`][match] objects, a number of [`Registration`][registration] objects, and other optional information.

## Tournament object

<table class="fields"><tbody>
  <tr class="required">
    <th>name</th>
    <td class="type">String</td>
    <td>The tournament's name.</td>
  </tr>
  <tr class="optional">
    <th>site</th>
    <td class="type">TournamentSite</td>
    <td>Where this tournament happened, see below.</td>
  </tr>
  <tr class="optional">
    <th>start_date</th>
    <td class="type">String</td>
    <td>The tournament's start date, as an ISO 8601-formatted string in the tournament's local time zone.</td>
  </tr>
  <tr class="optional">
    <th>end_date</th>
    <td class="type">String</td>
    <td>The tournament's end date, as an ISO 8601-formatted string in the tournament's local time zone.</td>
  </tr>
  <tr class="optional">
    <th>first_playoff_round</th>
    <td class="type">Number</td>
    <td>The first round of this tournament's playoffs.</td>
  </tr>
  <tr class="optional">
    <th>players_per_side</th>
    <td class="type">Number</td>
    <td>The number of players per side during a game. If omitted, assume <code>4</code>.</td>
  </tr>
  <tr class="optional">
    <th>registrations</th>
    <td class="type"><nobr>Array <code><a href="{{ site.baseurl }}/registration">Registration</a></code></nobr></td>
    <td>The organizations registered to play in this tournament.</td>
  </tr>
  <tr class="optional">
    <th>matches</th>
    <td class="type"><nobr>Array <code><a href="{{ site.baseurl }}/match">Match</a></code></nobr></td>
    <td>The matches that took place in this tournament.</td>
  </tr>
</tbody></table>

## TournamentSite object

<table class="fields"><tbody>
  <tr class="optional">
    <th>name</th>
    <td class="type">String</td>
    <td>The tournament site's name.</td>
  </tr>
  <tr class="optional">
    <th>city</th>
    <td class="type">String</td>
    <td>The city/state/country of the tournament's site.</td>
  </tr>
</tbody></table>

[match]: {{ site.baseurl }}/match
[registration]: {{ site.baseurl }}/registration
