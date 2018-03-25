# B.One Hub Support Pages
This file explains how the support pages files are organized, and how users can create new pages, manage content, etc.

## Topics
- [Creating a new category](#creating-a-new-category)
- [Creating a new support page](#creating-a-new-support-page)
- [Formatting the page content](#formatting-the-page-content)
- [Running a local server](#running-a-local-server)
- [Generating the live pages](#generating-the-live-pages)

## Creating a new category
Each category has a dedicated folder. The folders are located in [_posts](https://github.com/lovelldies/b1hubsupport/tree/master/_posts).

1. Create a **new folder** with the **category name** in **lowercase**. This is where all the support pages for this category will go.
2. Create a new file with the following name `categoryname.md` in the `categories` folder, and add the following text into it:
   ```
   ---
   layout: posts
   catid: 5_DIGIT_CATEGORY_ID
   category: categoryname
   permalink: /categoryname/
   categorytitle: Category Name
   ---
   
   {{ content }}
   ---
   ```
3. Save the file.
4. Make sure to add the `categoryname` to the `cat_array` array, in the `index.md` file. This controls the order of the displayed categories.

## Creating a new support page
This section only guides you on how to create a new FAQ/Support page. The next section explains how to **format the page content**.

1. Navigate to the required **category** folder.
2. Create a new markdown file, using the following naming convention: `YYYY-DD-MM-name-of-the-faq-or-page-title.md`.
For example: `2017-07-20-does-bone-use-a-cloud.md`. The date should be the date on which the page is being created.
3. All pages should contain the below text (called [Front Matter](https://jekyllrb.com/docs/frontmatter/)) at the beginning of the file. 
```
---
layout: post
postid: 5_DIGIT_POST_ID
catid: 5_DIGIT_CATEGORY_ID
categories: CATEGORY_NAME
title: TITLE_OF_THE_POST
---

PAGE_TEXT_GOES_HERE
```
Make sure to replace the `CATEGORY_NAME` and `TITLE_OF_THE_POST` with the relevant information. Also make sure to include both the `---` lines.

The `5_DIGIT_POST_ID`, is a 5 digit integer manually chosen so that you can control the order of the posts/FAQs on their respective category pages. The order of the posts are managed in [this spreadsheet](https://docs.google.com/spreadsheets/d/1d5qXSUv9GqUOlC9FJeIw_nP5kJrdOb-mo5kSg_SZdQM/edit).

`PAGE_TEXT_GOES_HERE` is where the FAQ/Support content will appear. We shall get to that in the next section. To better understand what we just did, have a look at this very simple example:
  - [Source File](https://raw.githubusercontent.com/lovelldies/b1hubsupport/master/_posts/general/2017-07-20-does-bone-use-a-cloud.md)
  - [Live Page](https://lovelldies.github.io/b1hubsupport/general/does-bone-use-a-cloud/)

## Formatting the page content
All page content can be written in [markdown](https://guides.github.com/features/mastering-markdown/) or plain HTML. We shall stick to markdown, which is much easier to understand.

#### Formatting text
* **Bold** :
  ```
  **bold text**
  ```

* *Italics* :
  ```
  *italics*
  ```

#### Hyerlinks
* [Link text](http://www.example.com) :
  ```
  [Link text](http://www.example.com)
  ```

#### Images
Make sure to upload images into the ```/assets/img/support-images/``` folder, the directory structure of which can be viewed [here](https://github.com/lovelldies/b1hubsupport/tree/master/assets/img/support-images).
* If your image is in the root folder, use:
  ```
  ![Image Alt Text]({{ site.img }}/IMAGE_FILE_NAME.EXT)
  ```
* If you are using a sub-folder to organize images, use:
  ```
  ![Image Alt Text]({{ site.img }}/SUB_FOLDER_NAME/IMAGE_FILE_NAME.EXT)
  ```
  ![Image Alt Text](http://lorempixel.com/100/100/)

### Bullet Points
* Ordered list (with numbers) are pretty straight forward:
  1. Line of text #1.
  2. Line of text #2.
  3. Line of text #3.

  *is written as:*
  ```
  1. Line of text #1.
  2. Line of text #2.
  3. Line of text #3.
  ```
* Un-ordered list (without numbers):
  * Line of text #1.
  * Line of text #2.
  * Line of text #3.

  *is written as:*
  ```
  * Line of text #1.
  * Line of text #2.
  * Line of text #3.
  ```
To learn more, here is a cheatsheet for writing [Markdown](https://www.markdownguide.org/cheat-sheet).

## Running a local server
- The support pages are generated using [Jekyll](https://jekyllrb.com/), setup instructions for which are on the website.
- The repository to clone is [https://github.com/lovelldies/b1hubsupport](https://github.com/lovelldies/b1hubsupport).
- After making any changes, you run ```jekyll serve``` which launches a local server.

## Generating the live pages
- Once you are satisfied with what you see on the local server, you can build the live pages but running ```jekyll build --config "_config.yml,_config_live.yml"```
- This generates a ```_site``` folder. Copy the contents of this folder to the ```support``` directory using FTP.