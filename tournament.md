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
  <tr>
    <th>short_name</th>
    <td class="type">String</td>
    <td>An abbreviated version of the tournament's <code>name</code>. If omitted, assume the same as the <code>name</code>.</td>
  </tr>
  <tr class="optional">
    <th>site</th>
    <td class="type">TournamentSite</td>
    <td>Where this tournament happened; see below.</td>
  </tr>
  <tr>
    <th>scoring_rules</th>
    <td class="type">ScoringRules</td>
    <td>Validation rules for scoring matches in this tournament; see below.</td>
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
    <th>registrations</th>
    <td class="type"><nobr>Array <code><a href="{{ site.baseurl }}/registration">Registration</a></code></nobr></td>
    <td>The organizations registered to play in this tournament.</td>
  </tr>
  <tr class="optional">
    <th>matches</th>
    <td class="type"><nobr>Array <code><a href="{{ site.baseurl }}/match">Match</a></code></nobr></td>
    <td>The matches that took place in this tournament.</td>
  </tr>
  <tr class="optional">
    <th>rankings</th>
    <td class="type"><nobr>Array <code><a href="{{ site.baseurl }}/ranking">Ranking</a></code></nobr></td>
    <td>The rankings used at this tournament.</td>
  </tr>
</tbody></table>

## TournamentSite object

<table class="fields"><tbody>
  <tr>
    <th>name</th>
    <td class="type">String</td>
    <td>The tournament site's name.</td>
  </tr>
  <tr class="optional">
    <th>place</th>
    <td class="type">String</td>
    <td>The location of the tournament. Free-form; the purpose is to enable people to find the site.</td>
  </tr>
  <tr class="optional">
    <th>latitude</th>
    <td class="type">Number</td>
    <td>The latitude of the tournament's site (for geolocation).</td>
  </tr>
  <tr class="optional">
    <th>longitude</th>
    <td class="type">Number</td>
    <td>The longitude of the tournament's site (for geolocation).</td>
  </tr>
</tbody></table>

## ScoringRules object

<table class="fields"><tbody>
  <tr>
    <th>name</th>
    <td class="type">String</td>
    <td>The name for this set of scoring rules.</td>
  </tr>
  <tr class="optional">
    <th>teams_per_match</th>
    <td class="type">Number</td>
    <td>The number of teams that participates in each match. If omitted, assume <code>2</code>.</td>
  </tr>
  <tr class="optional">
    <th>max_players_per_side</th>
    <td class="type">Number</td>
    <td>The maximum number of players that may be active at once, per team, in a match. If omitted, assume <code>4</code>.</td>
  </tr>
  <tr class="optional">
    <th>regulation_tossup_count</th>
    <td class="type">Number</td>
    <td>The standard number of tossups heard in a match. If omitted, assume <code>20</code>.</td>
  </tr>
  <tr class="optional">
    <th>maximum_regulation_tossup_count</th>
    <td class="type">Number</td>
    <td>The maximum number of tossups heard in a match that does not go into overtime. (Different from <code>regulation_tossup_count</code> for tournaments that used timed matches.</code>.) If omitted, assume <code>20</code>.</td>
  </tr>
  <tr class="optional">
    <th>total_divisor</th>
    <td class="type">Number</td>
    <td>The largest integer that is guaranteed to be a factor of a valid final score for one team in one match. If omitted, assume <code>5</code>. If present, must be a positive integer.</td>
  </tr>
  <tr class="optional">
    <th>maximum_bonus_score</th>
    <td class="type">Number</td>
    <td>The maximum possible score on a single bonus. Omitting this means there are no bonuses. If present and <code>bonus_divisor</code> is present, must be divisible by <code>bonus_divisor</code>.</td>
  </tr>
  <tr class="optional">
    <th>bonus_divisor</th>
    <td class="type">Number</td>
    <td>The largest integer that is guaranteed to be a factor of a valid score on a single bonus. If omitted but <code>maximum_bonus_score</code> is present, assume <code>10</code>. If present, must be a positive integer.</td>
  </tr>
  <tr class="optional">
    <th>bonuses_bounce_back</th>
    <td class="type">Boolean</td>
    <td><code>true</code> if the non-controlling team has an opportunity to answer parts of a bonus that the controlling team did not answer correctly; <code>false</code> if not. If omitted but <code>maximum_bonus_score</code> is present, assume <code>false</code>.</td>
  </tr>
  <tr class="optional">
    <th>lightnings_per_team_per_match</th>
    <td class="type">Number</td>
    <td>The number of lightning rounds received by each team in each game. If omitted, assume <code>0</code>.</td>
  </tr>
  <tr class="optional">
    <th>maximum_lightning_score</th>
    <td class="type">Number</td>
    <td>The maximum possible score on a single lightning round. If omitted but <code>lightnings_per_team_per_match</code> is present and positive, assume <code>100</code>.</td>
  </tr>
  <tr class="optional">
    <th>lightning_divisor</th>
    <td class="type">Number</td>
    <td>The largest integer that is guaranteed to be a factor of a valid score on a single lightning round. If omitted but <code>lightnings_per_team_per_match</code> is present and positive, assume <code>10</code>. If present, must be a positive integer.</td>
  </tr>
  <tr class="optional">
    <th>lightnings_bounce_back</th>
    <td class="type">Boolean</td>
    <td><code>true</code> if the non-controlling team has an opportunity to answer parts of a lightning round that the controlling team did not answer correctly; <code>false</code> if not. If omitted but <code>lightnings_per_team_per_match</code> is present and positive, assume <code>true</code>.</td>
  </tr>
  <tr class="optional">
    <th>answer_types</th>
    <td class="type"><nobr>Array <code><a href="{{ site.baseurl }}/answer_type">AnswerType</a></code></nobr></td>
    <td>The different answer types possible in this tournament.</td>
  </tr>
</tbody></table>

[match]: {{ site.baseurl }}/match
[registration]: {{ site.baseurl }}/registration
