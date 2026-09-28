# votemapper-marketing-images

**Public.** Social images for VoteMapper, hosted here so Buffer can fetch them by URL.
Buffer's API only accepts images by public URL; the marketing repo
(`votemapper-marketing`, private) cannot serve them.

Files are published by the Content Engine (`votemapper-marketing/content-engine`)
when a human approves an item, and by the feature-launch carousels in
`votemapper-marketing/Marketing/Social/` (contentIds starting `feat-`) once they are
reviewed and merged, and by App Store screenshot sets from
`votemapper-marketing/Marketing/screenshots-ppo-*` (contentIds starting `shots-`) once a
human has checked they show the current UI. Nothing else writes here. **Never publish a
screenshot of the pre-Canvass UI** (anything before app 1.40, Aug 27, 2026).

## Layout

```
votemapper/<contentId>/9x16/01.jpg …   1080×1920, TikTok photo posts, Reels, Stories
votemapper/<contentId>/4x5/01.jpg …    1080×1350, Instagram and Threads
votemapper/<contentId>/iphone/01.jpg … 1320×2868, App Store iPhone screenshot (shots-* only)
votemapper/<contentId>/ipad/01.jpg …   2064×2752, App Store iPad screenshot (shots-* only)
```

`iphone` and `ipad` are App Store sizes, not social crops. They suit X, Threads, Bluesky,
Facebook and LinkedIn. They fall outside Instagram's feed range (4:5 to 1.91:1), and the
iPhone ones are taller than 9:16, so Instagram and TikTok need a `4x5` / `9x16` render.

| contentId | Formats | What it is |
|---|---|---|
| `shots-20260927-color-panorama` | iphone, ipad (6 each) | October 2026 PPO treatment: Canvass colour, serif headlines |
| `shots-20260927-decision-desk` | iphone, ipad (6 each) | October 2026 PPO treatment: navy election-night broadcast look |
| `shots-20260927-group-chat` | iphone, ipad (6 each) | October 2026 PPO treatment: the app inside a Messages thread |
| `shots-20260915-ppo-146` | iphone (8) | The 1.46 PPO set that went live on Sep 15, 2026 |

URL form:

```
https://raw.githubusercontent.com/ColinScattergood/votemapper-marketing-images/main/votemapper/<contentId>/<format>/<NN>.jpg
```

## Rules

1. **Approved items only.** Never push drafts or rejected items. Everything in this
   repo's history is public for good.
2. **Never move, rename, overwrite or delete a published file.** A queued Buffer post
   may fetch its image at publish time. A changed item gets a new contentId, and so
   a new folder.
3. **Images only.** No captions, manifests, analytics or anything else from the
   private marketing repo.
