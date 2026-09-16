# AWS Student Builder Group @ Seneca Polytechnic

The home base for our club: who we are, how we run things, and a folder for every event we host.

New to the team? Read this page, then open [`sessions/`](sessions/) to see what is coming up.

## What is an AWS Student Builder Group?

AWS Student Builder Groups are student-run clubs supported by Amazon Web Services. Members learn cloud by building real things on AWS and helping each other out.

We are the **Seneca Polytechnic** group, based at Newnham Campus in Toronto. We talk about everything that touches cloud: AWS, DevOps, system design, and getting hired.

## Find us

| Where | Link |
|---|---|
| All our links | [linktr.ee/awsseneca](https://linktr.ee/awsseneca) |
| Event RSVPs (Meetup) | [meetup.com/aws-sbg-at-seneca-polytechnic-newnham-campus](https://www.meetup.com/aws-sbg-at-seneca-polytechnic-newnham-campus/) |
| LinkedIn | [aws-student-builder-seneca-poly](https://www.linkedin.com/company/aws-student-builder-seneca-poly/) |
| SSF club signup | [clubs.ssfinc.ca/SBG](https://clubs.ssfinc.ca/SBG/club_signup) |

Events are free and open to any Seneca student. You do not need to know anything about AWS to join.

## What we focus on

The year follows one progression, with the AWS Certified Cloud Practitioner exam as the thread through every session:

- **Foundation**: what the cloud is, core AWS services, your first deploy
- **Go deeper**: system design on AWS, careers in cloud
- **Build**: DevOps, CI/CD, a hackathon
- **Ship**: wrap up the year and hand the club to the next leaders

Event formats we use: talks, hands-on workshops, career panels, quiz nights, and a hackathon.

## How we work

- Contribution over attendance
- Engineers teaching engineers
- No gatekeeping. Curiosity is the only credential
- Ideas from anyone, not just the exec team
- Build in public

## Get involved

You do not need to be on the exec team to contribute.

- **Have an idea for an event?** [Open an event idea](https://github.com/aws-seneca/info/issues/new?template=event-idea.yml).
- **Want to teach something?** [Offer a talk or demo](https://github.com/aws-seneca/info/issues/new?template=talk-proposal.yml). The best sessions come from people who just figured something out.
- **Spotted something wrong here?** [Report it](https://github.com/aws-seneca/info/issues/new?template=fix-or-update.yml), or fix it yourself with a pull request.

## Core team

| Name | Role |
|---|---|
| Bilal | President |
| Daksh | Exec team |
| Hatim | Exec team |
| Sneha | Exec team |
| Maritza | Marketing |
| Mohit | Marketing |
| Cynthia | Marketing |

Update this table when the team changes. Roles open up every term.

## Repository layout

```
info/
├── README.md                        ← you are here
├── CONTRIBUTING.md                  ← how to add or update a session
├── .github/                         ← issue forms, PR template, automatic checks
├── scripts/
│   └── check-sessions.sh            ← checks folder names and required files
├── templates/
│   └── session/                     ← copy this folder to start a new session
│       ├── README.md
│       ├── deck.md
│       └── recap.md
└── sessions/
    ├── README.md                    ← index of every session
    └── 2026-fall/                   ← one folder per term
        └── 2026-09-16-kickoff/      ← one folder per session: date, then name
            ├── README.md            ← details, run of show, checklist
            ├── deck.md              ← slide text and speaker notes
            ├── 2026-09-16-kickoff.pptx
            └── recap.md             ← filled in after the event
```

### Naming rules

| What | Pattern | Example |
|---|---|---|
| Term folder | `YYYY-term` | `2026-fall`, `2027-winter` |
| Session folder | `YYYY-MM-DD-short-name` | `2026-10-07-aws-101` |
| Slides file | same name as the session folder | `2026-10-07-aws-101.pptx` |

Date first keeps sessions in order when sorted. Naming the slides after the folder means a downloaded file still says which event it belongs to.

## Starting a new session

```bash
cp -r templates/session sessions/2026-fall/2026-10-07-aws-101
```

Then fill in the new `README.md` and add a row to [`sessions/README.md`](sessions/README.md). Full steps are in [CONTRIBUTING.md](CONTRIBUTING.md).

## Club rules to keep in mind

- **SSF approval comes first.** Only registered SSF officers can submit events. Submit before announcing a date.
- **No events in the first three weeks of term.** SSF rule introduced in fall 2026.
- **Meetup is the RSVP link.** Use it in every post, not calendar links.
- **Clean up AWS resources.** Delete demo buckets, instances, and anything else that bills once the event is over.

## What does not go in this repo

This repository is public. Do not commit:

- Personal emails, phone numbers, or home addresses
- Staff, sponsor, or Amazon contact details
- Budget numbers, receipts, AWS credit codes, or exam vouchers
- AWS account IDs, access keys, passwords, or tokens
- Links to private Drive folders, meeting rooms, or internal chat logs
- Build scripts or source files used to make slides. Commit the finished `.pptx` only.

Keep those in the team's private Drive or Discord.
