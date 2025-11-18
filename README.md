# Imgur Scraper
> A powerful Imgur scraping tool for collecting posts, tags, comments, and user-generated media at scale. Built for speed and reliability, this Imgur scraper helps you extract structured post data, engagement metrics, and user details with minimal effort.
> Ideal for researchers, analysts, meme curators, and developers needing high-volume Imgur datasets.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/za2122/footer-section/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/devpilot1" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>imgur-scraper</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
This project provides a robust solution for collecting detailed information from Imgur, including posts, images, user feeds, tags, and full comment threads.
It solves the challenge of Imgur’s limited public API by enabling reliable, structured web data extraction.
Designed for developers, data analysts, and automation engineers who need organized Imgur data for research, dashboards, or content pipelines.

### Key Extraction Capabilities
- Handles search pages, tag pages, gallery pages, and user profiles.
- Retrieves full post metadata including engagement numbers and virality metrics.
- Extracts complete comment threads with nested replies.
- Supports pagination, item limits, and interval-based scraping.
- Optimized for high-speed, low-resource scraping at scale.

## Features
| Feature | Description |
|---------|-------------|
| Search scraping | Scrape posts from any keyword with sorting and filter options. |
| Tag scraping | Collect all posts under any Imgur tag instantly. |
| User post scraping | Retrieve every post uploaded by any Imgur user. |
| Comment extraction | Capture full comment threads including replies and metadata. |
| Post detail scraping | Extract comprehensive metadata, media assets, and engagement stats. |
| Pagination support | Control depth of scraping with `endPage` and `maxItems`. |
| Extendable mapping | Use custom functions to shape or enrich output. |

---

## What Data This Scraper Extracts
| Field Name | Field Description |
|-------------|------------------|
| id | Unique ID of the Imgur post. |
| type | Type of item (post, album, etc.). |
| title | Title of the Imgur post. |
| description | Text description attached to the post. |
| numberOfViews | Total number of views. |
| numberOfUpvotes | Count of upvotes. |
| numberOfDownvotes | Count of downvotes. |
| numberOfFavorites | Times the post was favorited. |
| numberOfComments | Total comment count. |
| virality | Computed virality score. |
| score | Engagement score. |
| isAlbum | Indicates if the post is an album. |
| createdAt | Timestamp of post creation. |
| account | Detailed poster profile info. |
| tags | List of associated tags. |
| media | Array of media objects (images/videos). |
| comments | Nested comment structure with replies. |

---

## Example Output
Example:
    [
        {
          "type": "post",
          "id": "JBTJqu2",
          "title": "holiday",
          "numberOfViews": 8578,
          "numberOfUpvotes": 23,
          "numberOfDownvotes": 5,
          "numberOfPoints": 18,
          "numberOfComments": 6,
          "numberOfFavorites": 1,
          "url": "https://imgur.com/gallery/JBTJqu2",
          "tags": ["storytime", "funny", "awesome"],
          "media": [
              {
                "mime_type": "video/mp4",
                "url": "https://i.imgur.com/dK9p4A1.mp4",
                "width": 960,
                "height": 540
              }
          ],
          "comments": [
              {
                "id": 1681576587,
                "comment": "https://youtu.be/q-qqrGtlHkg",
                "upvote_count": 2,
                "comments": []
              }
          ]
        }
    ]

---

## Directory Structure Tree
    imgur-scraper-scraper/
    ├── src/
    │   ├── main.js
    │   ├── extractors/
    │   │   ├── post_parser.js
    │   │   ├── media_handler.js
    │   │   └── comment_parser.js
    │   ├── utils/
    │   │   ├── pagination.js
    │   │   └── request_limiter.js
    │   ├── config/
    │   │   └── settings.example.json
    │   └── outputs/
    │       └── dataset_exporter.js
    ├── data/
    │   ├── sample_inputs.json
    │   └── sample_output.json
    ├── docs/
    │   └── reference.md
    ├── tests/
    │   ├── parser.test.js
    │   └── utils.test.js
    ├── LICENSE
    ├── package.json
    └── README.md

---

## Use Cases
- **Analysts** collect large Imgur datasets to study meme trends, engagement metrics, or viral content patterns.
- **Researchers** gather longitudinal post data for behavioral or cultural analysis.
- **Content creators** compile media collections for inspiration, redistribution, or automated curation.
- **Developers** integrate Imgur scraping into apps that track topics, users, or tags.
- **Media teams** extract comments and engagement signals for sentiment analysis.

---

## FAQs

**Q: Can it scrape nested comments?**
Yes. The scraper returns complete comment threads with replies embedded in a structured hierarchy.

**Q: What types of Imgur URLs are supported?**
Search pages, tag pages, gallery posts, and user profile pages can all be provided as start URLs.

**Q: How do I limit the number of items scraped?**
Use the `maxItems` parameter to stop scraping after a desired number of results.

**Q: Can I modify the output structure?**
Yes. `extendOutputFunction` and `customMapFunction` allow custom transformations on each item.

---

## Performance Benchmarks and Results
- **Primary Metric:** Scrapes ~100 listings in about 2 minutes on average under normal conditions.
- **Reliability Metric:** Maintains a high success rate with stable handling of pagination and large result sets.
- **Efficiency Metric:** Uses approximately 0.025–0.03 compute units for every 100 processed listings.
- **Quality Metric:** Outputs highly complete datasets with consistent metadata, nested comments, and precise media attributes.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/za2122/footer-section/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        “Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time.”
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/za2122/footer-section/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        “Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on.”
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtube.com/shorts/6AwB5omXrIM" target="_blank">
        <img src="https://github.com/za2122/footer-section/blob/main/media/review3.gif" alt="Review 3" width="35%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        “Exceptional results, clear communication, and flawless delivery. Bitbash nailed it.”
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
