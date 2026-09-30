# votemapper-marketing-images

**Public.** VoteMapper marketing media — images *and* video — that has to be reachable by
URL. Buffer's API only accepts media by public URL; the marketing repo
(`votemapper-marketing`, private) cannot serve it. That is this repo's whole purpose:
media that needs to be public so the marketing tooling can get at it.

Files are published by the Content Engine (`votemapper-marketing/content-engine`)
when a human approves an item, by the feature-launch carousels in
`votemapper-marketing/Marketing/Social/` (contentIds starting `feat-`) once they are
reviewed and merged, by App Store screenshot sets from
`votemapper-marketing/Marketing/screenshots-ppo-*` (contentIds starting `shots-`) once a
human has checked they show the current UI, and by the rendered video ads from
`votemapper-marketing/Scripts/ads/` (contentIds starting `ad-`) once a human has watched
the cut. Nothing else writes here. **Never publish a screenshot of the pre-Canvass UI**
(anything before app 1.40, Aug 27, 2026).

## Layout

```
votemapper/<contentId>/9x16/01.jpg …   1080×1920, TikTok photo posts, Reels, Stories
votemapper/<contentId>/4x5/01.jpg …    1080×1350, Instagram and Threads
votemapper/<contentId>/iphone/01.jpg … 1320×2868, App Store iPhone screenshot (shots-* only)
votemapper/<contentId>/ipad/01.jpg …   2064×2752, App Store iPad screenshot (shots-* only)
```

Video sits in the same aspect-ratio folders as the stills it would replace, as
`NN.mp4`, with its poster frame beside it as `NN-poster.jpg` so a post can supply a
thumbnail:

```
votemapper/<contentId>/9x16/01.mp4         1080×1920 H.264 + AAC, Reels / TikTok / Threads
votemapper/<contentId>/9x16/01-poster.jpg  the same cut's poster frame
```

`iphone` and `ipad` are App Store sizes, not social crops. They suit X, Threads, Bluesky,
Facebook and LinkedIn. They fall outside Instagram's feed range (4:5 to 1.91:1), and the
iPhone ones are taller than 9:16, so Instagram and TikTok need a `4x5` / `9x16` render.

| contentId | Formats | What it is |
|---|---|---|
| `ad-20260930-senate-six-races` | 9x16 video (28 s) | Ad 1 · Six Senate tossups, the chamber lands |
| `ad-20260930-since-1788` | 9x16 video (30 s) | Ad 3 · Sixty presidential elections, one map each |
| `ad-20260930-forecast-on-the-record` | 9x16 video (28 s) | Ad 4 · Seal a Senate forecast, get a verification link |
| `ad-20260930-house-218` | 9x16 video (29 s) | Ad 2 · 435 districts, 218 for a majority |
| `shots-20260927-color-panorama` | iphone, ipad (6 each) | October 2026 PPO treatment: Canvass colour, serif headlines |
| `shots-20260927-decision-desk` | iphone, ipad (6 each) | October 2026 PPO treatment: navy election-night broadcast look |
| `shots-20260927-group-chat` | iphone, ipad (6 each) | October 2026 PPO treatment: the app inside a Messages thread |
| `shots-20260915-ppo-146` | iphone (8) | The 1.46 PPO set that went live on Sep 15, 2026 |

URL form:

```
https://raw.githubusercontent.com/ColinScattergood/votemapper-marketing-images/main/votemapper/<contentId>/<format>/<NN>.<ext>
```

## Rules

1. **Approved items only.** Never push drafts or rejected items. Everything in this
   repo's history is public for good.
2. **Never move, rename, overwrite or delete a published file.** A queued Buffer post
   may fetch its media at publish time. A changed item gets a new contentId, and so
   a new folder.
3. **Media only.** Images and video, and nothing else — no captions, manifests,
   analytics or anything else from the private marketing repo.
4. **Keep video small.** A social cut is seconds long and a few MB; this is a git repo,
   not a CDN. App previews and other long-form video stay in the marketing repo unless
   something actually needs to fetch them by URL.
