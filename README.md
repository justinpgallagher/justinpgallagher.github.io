# mariaines.github.io

## How to update site data

Data for the research and teaching pages are defined in `_data/<page>.yml`. [YAML](https://learnxinyminutes.com/docs/yaml/) is a
human-friendly data serialization format. It looks like this:

```yaml
- key: value
  another_key: "Another value"
- key: value for the 2nd item
  nested_key:
    - item: blah
    - item: blah 2
```

For example, `_data/teaching.yml` contains 3 top-level items, each with a number of
key/value pairs:

```yaml
- name: "ECON 368: Environmental Economics"
  link: http://weatherhead.case.edu/academics/courses/ECON368
  syllabus: pdfs/ECON368-syllabus-fall-2016.pdf
  youtube: https://www.youtube.com/watch?v=Vyeqg4RxYPI
  description: "Economic models and reasoning provide a valuable lens through which to view many of the most intractable and perplexing environmental problems. The objective of this class is to apply the tools of a typical introductory or intermediate microeconomics course to topics involving the natural environment. That is, we will view environmental topics from the perspective of an economist. Topics that will be covered in this class include: Market failure in the case of externalities and public goods provision, Management of renewable resources, Cost-effective pollution control, and Energy use and global climate change. We will take the tools from the classroom and apply them to the most pressing environmental problems including: Air and water pollution, Endangered species, Valuation of the natural environment, Fossil fuel use, and Business sustainability."

- name: "ECON 326: Econometrics"
  link: http://weatherhead.case.edu/academics/courses/ECON326
  syllabus: pdfs/ECON326-syllabus-spring-2017.pdf
  description: "Econometrics is the application of statistics to empirical economic analysis. One way of testing the validity of economic theories is to gather data and apply statistical tests to see if the data support the theory. These data are usually gathered by observing actual economies, firms and consumers, rather than by performing experiments in a laboratory. Because economic analysts lack the precision and control of the laboratory, they must compensate by adjusting their statistical procedures. In this class, we will concentrate on regression analysis, which is the basic tool of the economic researcher. We will study the assumptions commonly made in the application of this technique, the consequences of violating these assumptions, and the corrections that can be made. Students will have a chance to formulate and test their own hypotheses using econometric software available for personal computers."

- name: "ECON 327: Advanced Econometrics"
  link: http://weatherhead.case.edu/academics/courses/ECON327
  syllabus: pdfs/ECON327-syllabus-spring-2016.pdf
  youtube: https://www.youtube.com/watch?v=jDF4-ZSY1k4
  description: "This class builds on the foundations of applied regression analysis developed in ECON 326. The goal of the class is to equip students with the tools to conduct a causal analysis of a hypothesis in a variety of settings. Topics will include causality, panel and time series data, instrumental variables and quasi-experiments, semi- and non-parametric methods, and treatment evaluation."
```

This data is referenced in the html pages like this:
```html
{% for course in site.data.teaching %}
  <li>{{ course.name }}</li>
{% endfor %}
```

So, to add or edit a course, just update the yaml file. A couple things to note:
- Indentation is important, and is used to represent relationships between data layers
- Colons are important. If you want a colon in a value, enclose the whole value in quotes:
  ```yaml
  key: "My value: with a colon"
  ```
- You can nest fields
- Lists are created by using dashes. Items are part of the same list if they are at the same indentation level.
- You can use (simple) html in yaml fields. This is useful for including links or styling, e.g. in a course description:
  ```yaml
  description: "Go to <a href='...'>this link</a>"
  ```

## Troubleshooting

Hopefully you won't run into problems if you're just editing the yaml data files. If you want to change something significant,
