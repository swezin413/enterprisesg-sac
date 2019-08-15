---
layout: leftnav-page-content
title: Brochures-Test
permalink: /resources/brochures-test
collection_name: resources

brochures:
  imgFolderPath: /images/brochures/
  docFolderPath: /files/brochures/
  categories:
    - title: "Commemorative Booklet: 50 Years of Quality and Standards"
      list:    
      - img: Comm-Book-2016.png
        url: https://spring.enterprisesg.gov.sg/Resources/Documents/50_years_of_quality_and_standards/web/html5/index.html
    - title: "SAC Brochures"
      list:    
      - name: "SAC Booklet"
        img: SAC-Booklet.jpg
        doc: SAC-Booklet.pdf
      - name: "Accreditation Scheme for Laboratories"
        img: SAC-Brochures-LA.jpg
        doc: SAC-Brochure-Accreditation-Scheme-for-Laboratories.pdf
      - name: "Accreditation Scheme for Inspection Bodies"
        img: SAC-Brochures-IB.jpg
        doc: SAC-Brochure-Accreditation-Scheme-for-Inspection-Bodies.pdf 
      - name: "Accreditation Scheme for Management System Certification Bodies"
        img: SAC-Brochures-MS.jpg
        doc: SAC-Brochure-Accreditation-Scheme-for-Managament-System-Certification-Bodies.pdf 
      - name: "Accreditation Scheme for Product Certification Bodies"
        img: SAC-Brochures-PC.PNG
        doc: SAC-Brochure-Accreditation-Scheme-for-Product-Certification-Bodies.pdf
      - name: "Good Laboratory Practice Compliance Programme"
        img: SAC-Brochures-GLP.jpg
        doc: SAC-Brochure-Good-Laboratory-Practice-Compliance-Programme.pdf 
      - name: "Accreditation Scheme for Personnel Certification Bodies"
        img: SAC-Brochures-PCB.jpg
        doc: SAC-Brochure-Accreditation-Scheme-for-Personnel-Certification-Bodies.pdf
      - name: "Accreditation Scheme for Proficiency Testing Providers"
        img: SAC-Brochures-PTP.jpg
        doc: SAC-Brochure-Accreditation-Scheme-for-Proficiency-Testing-Providers.pdf 
      - name: "SAC Accreditation Marks"
        img: SAC-Brochures-SAC-Accreditation Marks.jpg
        doc: SAC-Brochure-SAC-Accreditation-Mark.pdf 
      - name: "SAC Accreditation Programmes for the Building and Construction Industry"
        img: SAC-Brochures-Building_Construction.PNG
        doc: SAC-Accreditation-Programmes-for-the-Building-and-Construction-Industry.pdf   
    - title: "SAC Directory"
      list:    
      - img: SAC-Directory-Cover-1617.png
        doc: SAC-Directory-16-17-Final.pdf
    - title: "Other Brochures"
      list:    
      - name: "World Accreditation Day 2018"
        url: http://ilac.org/news-and-events/world-accreditation-day/    
      - name: "ILAC brochures"
        url: https://ilac.org/publications-and-resources/ilac-promotional-brochures/    
      - name: "IAF brochures"
        url: https://www.iaf.nu/articles/Promotional_Documents/300
        
---

{::nomarkdown}

{% assign pageBrochures = page.brochures %}
{% for category in pageBrochures.categories %}
  <h4 style="padding-left:1rem;">{{- category.title -}}</h4>
  {% assign numBrochures = category.list | size %}
  {% if numBrochures > 0  %}
    {% assign sample = category.list | first %}
    {% if sample.img %}
      <table class="brochures-table">
        {% for item in category.list %}
          {% assign image = pageBrochures.imgFolderPath | append: item.img %}
          {% if item.doc %}
              {% assign link = pageBrochures.docFolderPath | append: item.doc %}
            {% else if item.url %}
              {% assign link = item.url %}
            {% else %}
              {% assign link = '' %}
          {% endif %}
          <td><a href="{{- link -}}" target="_blank"><img src="{{- image -}}" />{% if item.name %}{{- item.name -}}{% endif %}</a></td>
        {% endfor %}
      </table>
    {% else %}
      <ul>
        {% for item in category.list %}
          {% if item.url %}
              {% assign link = item.url %}
            {% else if item.doc %}
              {% assign link = pageBrochures.docFolderPath | append: item.doc %}
            {% else %}
              {% assign link = '' %}
          {% endif %}
          <li><a href="{{- link -}}" target="_blank">{% if item.name %}{{- item.name -}}{% endif %}</a></li>
        {% endfor %}
      </ul>
    {% endif %}
  {% endif %}
{% endfor %}

{:/}