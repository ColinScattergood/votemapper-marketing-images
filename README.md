# votemapper-marketing-images

**Public.** Social images for VoteMapper, hosted here so Buffer can fetch them by URL.
Buffer's API only accepts images by public URL; the marketing repo
(`votemapper-marketing`, private) cannot serve them.

Files are published by the Content Engine (`votemapper-marketing/content-engine`)
when a human approves an item, and by the feature-launch carousels in
`votemapper-marketing/Marketing/Social/` (contentIds starting `feat-`) once they are
reviewed and merged. Nothing else writes here.

## Layout

```
votemapper/<contentId>/9x16/01.jpg …   1080×1920, TikTok photo posts, Reels, Stories
votemapper/<contentId>/4x5/01.jpg …    1080×1350, Instagram and Threads
```

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
