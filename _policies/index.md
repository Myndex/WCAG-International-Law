---
title: "Web Accessibility Laws & Policies"
nav_title: "Countries / Regions"
permalink: /policies/
order: 0
layout: sidenav
---


This page lists governmental policies related to web accessibility, although it is not a comprehensive or definitive listing. The information on this page is _not_ legal advice. If you have questions about the applicability of the policies to specific situations, please consult your legal council for the appropriate jurisdiction.


{% include excol.html type="start" id="xterms" %}

<h3>Terms used on this page</h3>

{% include excol.html type="middle" %}

### WCAG Version
- **WCAG 2.n:** Directly references the Web Content Accessibility Guidelines, which are as indicated, 2.0, 2.1, 2.2, or (future) 3.0.
- **Derived 2.n:** Used when a law or policy is largely based on some version of the Web Content Accessibility Guidelines (WCAG), but there may be additional exceptions and/or some requirements were excluded, modified, or additional non-WCAG requirements were added.
- **Other:** References other standards or own-legislation to satisfy legal or conformance requirements, but may reference WCAG documents as instructive, but not normative.
- **None:** No specific, actionable standard is put forth as a conformance requirement.

### Level
- **A AA AAA** For WCAG 2.x, the minimal allowed level, usually AA.
- **Bronze, Silver, Gold** For WCAG 3.x, the minimum allowed level, TBD.
- **Other** Some other conformance metric is used.

### Force
- **Recommend:** A best practices recommendation which is optional and has no force of law.
- **Policy:** A resolution that defines objectives of an entity, and may include methods and principles to adhere to.
- **Mandate:** A mandatory policy with required accessibility goals or implementation, but that is not regulated by law.
- **Regulation:** A regulation is a rule as defined by an agency or ministry, which has been given the legal authority to do so by the legislative body. Regulations usually have the force of law. For example, congress created a law that enables the FAA to regulate air traffic, and the FAA issues specific regulations, and can levy fines if certain regulations are not observed.
- **Law:** A law refers to a written statute or legal code which can be enforced. A law is usually codified through the legislation process, or in some instances as "case law" meaning court rulings that have the effect of law, and enforced by the governing body.

### Category
- **Equal Access:** Relating to non-discrimination and accessible accommodation requirements, mandates, or laws.
- **Accommodation:** Relating to basic accessible accommodation recommendations or policies.
- **Procurement:** Relating to accessibility requirements (law) or recommendations (policy) when the government purchases goods and services.
- **Proposed:** A law or policy that has not been enacted, but is under review and consideration.

### Applies to
- **Public sector:** Includes government as well as government-run or owned entities, and certain entities that receive government funding.
- **Regulated sector:** Private sector entities that are subject to significant governmental regulation, such as airlines or banking.
- **Public accommodation:** Private sector entities that provide goods or services directly to the public at large, such as stores, restaurants, theaters.
- **Private sector:** Businesses or organizations that are not part of the public sector nor public accommodation, including non-profit organizations. May have exclusions based on size.


{% include excol.html type="end" %}


<h2 id="xtable">Law and Policy Overview Table</h2>

<div>
  <details open>
    <summary>
    <h3 style="display:inline-block;">Filter policies to show:</h3>
    </summary>
    <div id="facets"></div>
  </details>
  
  <table class="sortable dense overviewtable">
    <caption>
      <h3>Overview Table:</h3>
      <div id="infos"></div>
    </caption>
    <thead>
    <tr>
      <th>Country or<br>Region</th>
      <th>WCAG<br>Version</th>
      <th>Level</th>
      <th>Web<br>Only</th>
      <th>Force</th>
      <th>Category</th>
      <th>Applies To</th>
      <th>Legislation</th>
      <th>Date</th>
    </tr>
    </thead>
    <tbody id="results">
      {% for policy in site.policies %}
      {% for p in policy.policies %}

      <tr data-updated="{{policy.updated}}">
        <td>{% assign curl = policy.country.en | slugify | prepend: '#x' %}
          {% include multilang-title.html title=policy.country url=curl %}</td>
        <td>{{p.wcagver}}</td>
        <td>{{p.wcaglevel}}</td>
        <td>{%if p.webonly == true %}yes{% else %}no{%endif%}</td>

        <td class="hyphenated">{{p.type}}</td>
        <td class="hyphenated">{{p.category}}</td>
        <td class="hyphenated">{{p.scope}}</td>


        <td><a href="{{ policy.url | prepend: site.baseurl }}#{{ p.title.en | slugify }}">{{p.title.en}}</a></td>
        <td>{{p.enactdate}}</td>
      </tr>

      {% endfor %}
      {% endfor %}
    </tbody>
  </table>
</div>

<script type="text/template" id="results-template">
  <tr>
    <td><a href="<%= obj.countryhref %>"><%= obj.title %></a></td>

    <td><%= obj.wcagver %></td>
    <td><%= obj.wcaglevel %></td>
    <td><%= obj.webonly %></td>
    <td class="hyphenated"><%= obj.type %></td>
    <td class="hyphenated"><%= obj.category %></td>
    <td class="hyphenated"><% if (obj.scope instanceof Array && obj.scope.length > 1) { %>
      <%= obj.scope.join(', ') %>
    <% } else { %>
      <%= obj.scope %>
    <% } %></td>

    <td><a href="<%= obj.policyhref %>"><%= obj.policyname %></a></td>
    <td><%= obj.enactdate %></td>
  </tr>
</script>


<script src="{{ "/policies/js/jquery.js" | relative_url }}"></script>
<script src="{{ "/policies/js/underscore.js" | relative_url }}"></script>
<script src="{{ "/policies/js/uri.js" | relative_url }}"></script>
<script src="{{ "/policies/js/facetedsearch.js" | relative_url }}"></script>
<script src="{{ "/policies/js/sorttable.js" | relative_url }}"></script>
<script>var path = "{{ "/" | relative_url }}";</script>
<script src="{{ "/policies/js/script.js" | relative_url }}"></script>
<style>@import url('{{ "/policies/css/policies.css" | relative_url }}');</style>
