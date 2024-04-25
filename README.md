# slidy-online

## Structure

```yaml
---
title: A title
author: quantt
date: 6.2.2024
header-includes: |
  <style>
  </style>
---
# Important notes
- Don't add arbitrary blank lines
```

**Remark**: No blank lines in this meta-data section

**See also**: [Other metadata variables](https://pandoc.org/MANUAL.html#variables)

## Minimalist CSS

- centered title
- comfortable margins
- great fonts for Vietnamese (body and headings)
- add color to headings
- add *shadow* class to make image border easier to notice

```css
    @import url(https://fonts.googleapis.com/css?family=Source+Serif+4:400,700,400italic);
    @import url(https://fonts.googleapis.com/css?family=Noto+Serif:400,700,400italic);
    .title { margin-left: 1em !important; }
    .slide {
      position: relative;
      margin-top: 20px !important;
      margin-left: 20px !important;
    }
    body {
      font-family: "Source Serif 4";
    }
    h1, h2, h3 {
      font-family: "Noto Serif";
      font-weight: normal;
      color: #002dc0; /* Ecotek blue */
      line-height: 1.25;
    }
    .shadow {
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3); /* Adjust the shadow values as needed */
    }
```

## Background

```css
    body {
      ...
      background-image: url('...');
      background-size: auto 100vh;
      background-repeat: repeat-y; /* to pdf print correctly */
    }
```

Some choices:

- [Ecotek background w/ logo](https://misc-public-0.s3.ap-southeast-2.amazonaws.com/Ecotek_presentation_background.png)
- [Student paper background](https://visme.co/blog/wp-content/uploads/2017/07/50-Beautiful-and-Minimalist-Presentation-Backgrounds-033.jpg)
- [A warm, Zen wall with a plant pot](https://24slides.com/presentbetter/content/images/wordpress/2020/07/image-from-rawpixel-id-580461-jpeg-1024x675.jpg)
- [A blue-pastel, professional geometric one](https://i.pinimg.com/originals/1d/e6/37/1de637aa47409992ad8817f3a9622086.jpg)

## Logo

CSS:

```css
    .logo {
      position: absolute;
      bottom: 40px;
      left: 20px;
      z-index: 999;
      width: 120px; /* Adjust width of logo as needed */
      height: auto; /* Maintain aspect ratio */
    }
```

Add in each slide:

```markdown
<img class="logo" src="https://misc-public-0.s3.ap-southeast-2.amazonaws.com/Ecotek_logo.png" alt="Logo">
```

Tips: use logo as background to avoid repetition and to allow correct printing.

## Table

CSS

```css
    table {
      border-collapse: collapse;
      border: 2px solid gray; /* Change border properties as needed */
    }
    td, th {
      border: 2px solid lightgray; /* Change cell border properties as needed */
    }
```

Content

```
+----------------------+-------+---------+---------+-------+---------+---------+----------+
| Hoạt động STEM       | Thứ 2 | Thứ 3   | Thứ 4   | Thứ 5 | Thứ 6   | Thứ 7   | Chủ nhật |
+:====================:+:=====:+:=======:+:=======:+:=====:+:=======:+:=======:+:========:+
| Làm quen thuật toán\ |       | 14h-15h |         |       |         | 9h-10h\ | 15h-16h  |
| 7-14 tuổi; 20 chỗ    |       |         |         |       |         | 16h-17h |          |
+----------------------+-------+---------+---------+-------+---------+---------+----------+
| Nhập môn robotics\   |       |         | 16h-17h |       | 10h-11h |         |          |
| 5-10 tuổi; 16 chỗ    |       |         |         |       |         |         |          |
+----------------------+-------+---------+---------+-------+---------+---------+----------+
```

Generate GFM table format: https://www.tablesgenerator.com/markdown_tables

## Centered slide

```css
    .page-centered {
      text-align: center;
      height: 80vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
```

Other variations: https://www.w3schools.com/css/css_align.asp

## Multi-column

```markdown
::: columns

:::: {.column width=33%}
left
::::

:::: {.column width=33%}
middle
::::

:::: {.column width=33%}
right
::::

:::
```

## CLI

Minimalist:

```bash
pandoc -t slidy -s <filename.md> -o <filename.html>
```

Include more elaborated styles:

```bash
pandoc -t slidy -sc <style.css> <filename.md> -o <filename.html>
```

## Useful links

[Online converter](https://pandoc.org/try/)

[Pandoc manual](https://pandoc.org/MANUAL.html#slide-shows)

[Other kinds of pandoc presentation](https://gist.github.com/johnloy/27dd124ad40e210e91c70dd1c24ac8c8)
