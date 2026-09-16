# CI/CD on AWS: from commit to live site

> **Status:** Idea
>
> Status values: Idea · Planning · Awaiting approval · Confirmed · Done · Recapped · Canceled

## Details

| | |
|---|---|
| **Date** | _TBD_ (proposed for a fall 2026 slot, 28 October or 18 November) |
| **Time** | 45 to 60 minutes: 25 to 40 minutes of teaching, 20 minutes held back for debugging help |
| **Venue** | _TBD_. In person works best. This is hands-on and loses the most over a video call |
| **Format** | Hands-on workshop |
| **Track** | Build |
| **Lead organizer** | _TBD_ |
| **Expected attendance** | _TBD_ |

## Links

| | |
|---|---|
| Event listing (Meetup) | _TBD_ |
| SSF club listing | _TBD_ |
| Research and technical design | [research.md](research.md) |
| Slide text and speaker notes | [deck.md](deck.md) |
| Slides (PowerPoint export) | _TBD: `YYYY-MM-DD-cicd-on-aws.pptx` once the folder has a date_ |
| Template repository | _TBD_ |
| Recording or photos | _TBD_ |
| Recap | [recap.md](recap.md) |

## Description

Push a commit and watch it go live on AWS on its own. You fork a small site, launch one CloudFormation stack, and wire up a GitHub Actions pipeline that deploys to S3 with no AWS keys stored anywhere. Then you break it on purpose and learn to read the error. Bring a laptop, a GitHub account, and an AWS account.

## What attendees leave with

A pipeline in their own GitHub repository that deploys every push to main to a public site, using short-lived OIDC credentials instead of stored access keys. They can explain the three parts: a commit triggers a build, the result is published automatically, and no human credentials were involved.

Not covered: containers, Kubernetes, multiple environments, or writing IAM policies from scratch. A follow-up container session is outlined in [research.md](research.md#the-follow-up-containers-to-production).

## Run of show

Based on 30 minutes of teaching. Stretch the middle segments if the slot allows 40.

| Time | Block | What happens |
|---|---|---|
| 0 to 4 | Deploy by hand, badly | Presenter uploads a file to S3 manually, slowly. Then asks who wants to do that eleven more times today |
| 4 to 8 | Fork and launch the stack | Everyone clicks. The stack builds while the next block runs |
| 8 to 14 | What just got created, and why it is safe | The OIDC token exchange, drawn out |
| 14 to 18 | Wire the secrets, read the workflow | Line by line. Nobody types it |
| 18 to 24 | Push and watch it land | Then push a second time, because the loop is the lesson |
| 24 to 28 | Break it on purpose | Remove `id-token: write`, watch it fail, read the real error, put it back |
| 28 to 30 | Teardown and what is next | Delete the stack. Point at the container session |
| +20 | Debug and help | Floating helpers work from the failure table in [research.md](research.md#failure-table-for-helpers) |

## Checklist

### Approvals and booking
- [ ] Topic and date agreed by the team
- [ ] Event submitted on the SSF platform
- [ ] SSF approval received
- [ ] Venue booked or online link created

### Promotion
- [ ] Event published on Meetup
- [ ] Posted on LinkedIn, Instagram, and Discord
- [ ] Pre-event email: GitHub account, AWS account, how to use the GitHub web editor

### Content
- [ ] Technical review of [research.md](research.md)
- [ ] Template repository built: `site/index.html`, `.github/workflows/deploy.yml`, a README with the five steps
- [ ] CloudFormation template built and a one-click launch URL made
- [ ] Action versions checked the week of the event
- [ ] Dry run on a fresh AWS account and a fresh GitHub account, every step timed
- [ ] Confirm the attendee AWS account route allows IAM OIDC providers
- [ ] Printed failure table for helpers
- [ ] Slide text drafted in `deck.md`

### Day of
- [ ] Two or three floating helpers
- [ ] Discord invite and feedback form links ready

### After
- [ ] Remind attendees to delete their stack
- [ ] `recap.md` filled in
- [ ] Status updated here and in `sessions/README.md`

## Open questions

1. Is a well-labelled `CreateOIDCProvider` parameter good enough, or is there a cleaner way to handle accounts that already have a GitHub OIDC provider?
2. Is 25 to 40 minutes of teaching realistic for the step list? Only a timed dry run will answer this.
3. Is the second push worth its two minutes? It is the first thing to cut if the room runs behind.
4. One session on S3, or two sessions that go all the way to containers?
