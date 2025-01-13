# A modern typst CV template

[![say thanks](https://img.shields.io/badge/Say%20Thanks-👍-1EAEDB.svg)](https://github.com/peterpf/modern-typst-resume/stargazers)

A customizable resume/CV template focusing on clean and concise presentation, with a touch of color.

**This template is available on [typst Universe](https://typst.app/universe/package/modern-resume)!**

## Requirements

To compile this project you need the following:

- [typst](https://github.com/typst/typst)
- [Roboto font family](https://fonts.google.com/specimen/Roboto)

## Compiling

Build the document once with

```bash
typst compile main.typ
```

Build the document whenever you save changes by running

```bash
typst watch main.typ
```

## Usage

The following code provides a minimum working example:

```typst
#import "@preview/modern-resume": *

#show: modern-resume.with(
  author: "John Doe",           // Optional parameter
  job-title: "Data Scientist",  // Optional parameter
  bio: lorem(5),                // Optional parameter
  avatar: image("avatar.png"),  // Optional parameter
  contact-options: (            // All entries are optional
    email: link("mailto:john.doe@gmail.com")[john.doe\@gmail.com],
    mobile: "+43 1234 5678",
    location: "Austria",
    linkedin: link("https://www.linkedin.com/in/jdoe")[linkedin/jdoe],
    github: link("https://github.com/jdoe")[github.com/jdoe],
    website: link("https://jdoe.dev")[jdoe.dev],
  ),
)

== Education

#experience-edu(
  title: "Master's degree",
  subtitle: "University of Sciences",
  task-description: [
    - Short summary of the most important courses
    - Explanation of master thesis topic
  ],
  date-from: "10/2021",
  date-to: "07/2023",
)

// More content goes here

```

See [main.typ](./main.typ) for a full example that showcases all available elements.

## Output examples

Example outputs for different color palettes:

| Default colors | Pink colors |
|:----------------:|:-------------:|
|![Default colors](./docs/images/demo-navy-dark.png) | ![Pink colors](./docs/images/demo-pink.png)|


## Customization

The template allows you to make it yours by defining a custom color palette.
By default, the template loads the configuration located at [template/config.yaml](https://github.com/peterpf/modern-typst-resume/blob/main/template/config.yaml):

```yaml
theme:
    primary: "#313C4E"
    secondary: "#222A33"
    accentColor: "#449399"
    textPrimary: "#000000"
    textSecondary: "#7C7C7C"
    textTertiary: "#ffffff"
```

You can change the location of the configuration file by passing it to the compiler via

```bash
typst compile file.typ --input config=path/to/config.yaml
```

## Elements

This section introduces the visual elements that are part of this template.

### Pills

Import this element from the template module with `pill`.

![pills](docs/images/pills.png)

```typst
#pill("German (native)")
#pill("English (C1)")
```

![pills filled](docs/images/pills-filled.png)

```typst
#pill("Teamwork", fill: true)
#pill("Critical thinking", fill: true)
```

### Educational/work experience

Import the elements from the template module with `experience-edu` and `experience-work` respectively.

![educational experience](docs/images/educational-experience.png)

```typst
#experience-edu(
  title: "Master's degree",
  subtitle: "University of Sciences",
  task-description: [
    - Short summary of the most important courses
    - Explanation of master thesis topic
  ],
  date-from: "10/2021",
  date-to: "07/2023",
)
```

![work experience](docs/images/work-experience.png)

```typst
#experience-work(
  title: "Full Stack Software Engineer",
  subtitle: [#link("https://www.google.com")[Some IT Company]],
  facility-description: "Company operating in sector XY",
  task-description: [
    - Short summary of your responsibilities
  ],
  date-from: "09/2018",
  date-to: "07/2021",
)
```

### Project

Import this element from the template module with `project`.


![project](docs/images/project.png)

```typst
#project(
  title: "Project 2",
  subtitle: "Data Visualization, Data Engineering",
  description: [
    - #lorem(20)
  ],
  date-from: "08/2022",
  date-to: "09/2022",
)
```

## Development

### Testing

Run the tests with

```bash
typst compile tests/test_lib.typ --root . --input config=tests/config.yaml
```

or with

```bash
nix flake check
```

## Acknowledgements

This project would not be what it is without:

- [Font Awesome Free](https://github.com/FortAwesome/Font-Awesome/) | providing the icons
