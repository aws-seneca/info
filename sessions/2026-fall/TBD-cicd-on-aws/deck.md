# CI/CD on AWS: slides

First outline, taken from the run of show in [README.md](README.md). Agree the wording here before anyone builds slides.

---

## Slide 1. Title

On screen:

```
From commit to live site
CI/CD on AWS
AWS Student Builder Group · Seneca Polytechnic
```

Notes: Laptops open, GitHub and AWS consoles signed in before we start.

---

## Slide 2. Deploying by hand

On screen:

```
Upload. Refresh. Check. Repeat.
Now do it eleven more times today.
```

Notes: Upload a file to S3 by hand, slowly, on screen. Four minutes. The point is to feel the work before automating it.

---

## Slide 3. What we are building

On screen: the architecture diagram from [research.md](research.md#architecture).

Notes: Push, token, short-lived credentials, sync, live URL. Start the stack launch now so it builds while we talk.

---

## Slide 4. No keys stored anywhere

On screen:

```
GitHub proves who is asking.
AWS hands back credentials that expire when the run ends.
The role can touch one bucket. Nothing else.
```

Notes: Most tutorials paste an access key into GitHub Secrets. That is how student projects become incidents. IAM will not even accept a trust policy that is not scoped to a repository.

---

## Slide 5. id-token: write

On screen:

```
permissions:
  id-token: write
```

```
It does not grant write access to anything.
It lets the job ask for an identity token.
```

Notes: The line everyone misreads.

---

## Slide 6. The workflow, line by line

On screen: the workflow file from [research.md](research.md#the-github-actions-workflow).

Notes: Read it together. Nobody types it. Call out `--delete`.

---

## Slide 7. Push and watch

On screen:

```
Edit site/index.html
Commit to main
Watch the Actions tab
Refresh your site
```

Notes: Then do it again. The loop is the lesson.

---

## Slide 8. Break it on purpose

On screen:

```
Delete id-token: write
Push
Read the actual error
Put it back
```

Notes: Everyone meets a red X within a month of their first real project. Seeing one on purpose makes the accidental one ordinary.

---

## Slide 9. Clean up and what is next

On screen:

```
Delete your stack
Next: containers to production
```

Notes: Delete the stack before leaving. The container session is where teardown protects real credits.

---

## Check before you present

- Action versions still current
- Dry run timed on a fresh AWS and GitHub account
