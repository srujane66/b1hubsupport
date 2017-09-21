# B.One Hub Support Pages
This file explains how the support pages files are organized, and how users can create new pages, manage content, etc.

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
categories: CATEGORY_NAME
title: TITLE_OF_THE_POST
---

PAGE_TEXT_GOES_HERE
```
Make sure to replace the `CATEGORY_NAME` and `TITLE_OF_THE_POST` with the relevant information. Also make sure to include both the `---` lines.

The `5_DIGIT_POST_ID`, is a 5 digit integer manually chosen so that you can control the order of the posts/FAQs on their respective category pages.

4. `PAGE_TEXT_GOES_HERE` is where the FAQ/Support content will appear. We shall get to that in the next section. To better understand what we just did, have a look at this very simple example:
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
Make sure to upload the images into the ```/assets/img/support-images/``` folder which can be viewed [here](https://github.com/lovelldies/b1hubsupport/tree/master/assets/img/support-images).
* ![Image Alt Text](http://lorempixel.com/100/100/) :
  ```
  ![Image Alt Text]({{ site.img }}/IMAGE_FILE_NAME.EXT)
  ```

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