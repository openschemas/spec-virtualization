---
layout: default
title: Openschemas Specifications
permalink: /
---
<h1>OpenSchemas Specifications</h1>

<p>This page contains drafts for an Openschemas specifications. Ongoing changes are published to the <a href="https://openschemas.github.io/specifications">official specifications </a> page. This page is updated with newly merged drafts from
the repository here. </p>
<p>Should you wish to contact the community to discuss our efforts please post an issue on <a href="https://www.github.com/openschemas/openschemas.github.io/issues" itemprop="email">the issues board</a>.</p>

<h2>Profiles</h2>

<p>The Openschemas' profiles define a community agreed layer over the Schema.org model providing additional constraints. These constraints capture (i) the information properties agreed by the community which are minimum (M), recommended (R), or optional (O), (ii) the cardinality of the property, i.e. whether it is expected to occur once or many times, and (iii) associated controlled vocabulary terms drawn from existing ontologies. </p>

<div class="bioschemas-spec-list-wrapper">
  <table class="bioschemas_spec_list" style="width: 100%; margin-left: auto; margin-right: auto; text-align: center;">
      <thead>
      <tr>
      <th>Name</th>
      <th style="text-align: center;">Use Cases</th>
      <th style="text-align: center;">Task &amp; Issues</th>
      <th style="text-align: center;">Examples</th>
      </tr>
      </thead>
      <tbody>
      {% assign prof_specs = site.specifications | where: 'spec_type', 'Profile'%}
      {% for spec in prof_specs %}
      <tr>
          {% assign date_time = spec.spec_info.version_date %}
          <th><a href="{{ site.github.url }}/specifications/{{ spec.name }}/" title="{{ spec.spec_info.subtitle }}">{{ spec.name }}</a><br />(v{{spec.spec_info.version}})<br />{{ date_time | date_to_long_string }}</th>
          <td class="spec_links">
            <a href="{{ spec.use_cases_url }}">
            <img src="https://openschemas.github.io/assets/images/use_case_spec.png" alt="View {{ spec.spec_info.name }} Use Cases"></a>
          </td>
          <td class="spec_links">
            {% if spec.gh_tasks == '' %}
            <a>
            <img src="https://openschemas.github.io/assets/images/specs_tasks.png" alt="{{ spec.spec_info.property }} Github Tasks or Issues" style="filter: grayscale(100%);">
            </a>
            {% else %}
            <a href="{{ spec.gh_tasks }}" target="_blank">
            <img src="https://openschemas.github.io/assets/images/specs_tasks.png" alt="Open Schemas {{ spec.spec_info.property }} Github Tasks or Issues">
            </a>
            {% endif %}
          </td>
          <td class="spec_links">
            {% if spec.spec_info.full_example == '' %}
            <a>
            <img src="https://openschemas.github.io/assets/images/spec_examples.png" alt="View {{ spec.spec_info.property }} Examples" style="filter: grayscale(100%);">
            </a>
            {% else %}
            <a href="{{spec.spec_info.full_example}}" target="_blank">
            <img src="https://openschemas.github.io/assets/images/spec_examples.png" alt="View {{ spec.spec_info.property }} Examples">
            </a>
            {% endif %}
          </td>
      </tr>
      {% endfor %}
      </tbody>
  </table>
</div>


<h2>Types</h2>
<p>We have found it necessary to propose some additional types to the Schema.org vocabulary. 
    These are specified below and are expected to be pushed up to Schema.org once they have stabilised. 
    These types are used as the generic base for some of the profile specifications, such as protein.
    Again, working versions are published in the <a href="/drafts">drafts</a> page.</p>

<table class="bioschemas_spec_list" style="width: 100%; margin-left: auto; margin-right: auto; text-align: center;">
    <thead>
    <tr>
        <th>Name</th>
        <th style="text-align: center;">Task &amp; Issues</th>
    </tr>
    </thead>
    <tbody>
    {% assign type_specs = site.types | where: 'spec_type', 'Type'%}
    {% for spec in  type_specs%}
    <tr>
        <th><a href="/types/{{spec.name}}" title="{{spec.subtitle}}">{{ spec.name }}</a><br />(v{{spec.version}})<br />{{spec.dateModified}}</th>
        <td class="spec_links">
            {% if spec.gh_tasks == '' %}
              <a>
                <img src="https://openschemas.github.io/assets/images/specs_tasks.png" alt="BioSchemas {{ spec.name }} Github Tasks or Issues" style="filter: grayscale(100%);">
              </a>
            {% else %}
              <a href="{{spec.gh_tasks}}">
                <img src="https://openschemas.github.io/assets/images/specs_tasks.png" alt="BioSchemas {{ spec.name }} Github Tasks or Issues">
              </a>
            {% endif %}
        </td>
    </tr>
    {% endfor %}
    </tbody>
</table>
