# Contributing

Thanks for helping make this roadmap better. This repository is a curated learning path, and curation
means every link costs someone a click — so the bar for adding or changing one is deliberately high.

## The ethics rule (non-negotiable)

This project is defensive-first. It teaches security work inside the legal frame: **only test systems you
own or have explicit written permission to test.**

- No content that enables attacks on systems the reader is not authorised to test — no exploit code
  aimed at third-party software, no payloads, no credential dumps, no target lists, no evasion or
  bypass recipes, no cracked or licence-dodging copies of commercial tools.
- Hands-on resources must point at a lab that is designed to be attacked (a practice platform, an
  intentionally vulnerable application, a wargame) or at the reader's own infrastructure.
- Offensive topics are welcome **only** in the context of Stage 7 — "offensive basics for defenders" —
  and only as authorized practice. Blue team content (detection, response, hardening) is the default.
- Anything that treats curiosity, good intent or "white hat" framing as permission will be declined.

## Link rules

1. **Verify the link with `curl` before opening the pull request.** A link that works in your browser and
   fails under `curl` is not verified:

   ```bash
   curl -sIL -o /dev/null -w '%{http_code}\n' --max-time 25 \
     -A 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/124 Safari/537.36' \
     '<your-url>'
   ```

   `200` is what we ship. `403` usually means bot protection on a real page — if you keep it, say so in
   your pull request and confirm you opened it yourself. `404`, `410` and `451` links are dropped.
   Some hosts answer `HEAD` with `404` while `GET` returns `200` (`portswigger.net` does this under
   `/web-security/*`), so re-check any `404` with `curl -sL` before dropping the URL.
2. **No affiliate, referral or tracking links.** No `?ref=`, no coupon codes, no link shorteners.
3. **No paywalled-only resources** unless the entry itself says so, plainly ("paid exam voucher",
   "free tier with a paid option", "employer-funded in most cases"). Free tiers and free-to-read
   material are preferred.
4. **Prefer primary sources**: official documentation, standards bodies (NIST, CISA, OWASP, MITRE,
   FIRST, CIS) and maintained open-source projects over listicles and SEO content.
5. **One link, one reason.** Every entry carries a short description saying what the reader gets from it.
   "Great resource!" is not a description.

## Structure rules

- Keep the eight-stage structure and the per-stage blocks: *What you will learn*, *Resources*,
  *Done when*.
- Keep the roadmap table in `README.md` in sync with the stage headings, and keep the anchors working
  (GitHub lowercases headings, strips punctuation and turns spaces into hyphens).
- Keep the **authorized testing only** line in every stage that involves hands-on offensive or scanning
  work. If you add such material to a stage that lacks the line, add the line too.
- `docs/` is intentionally small. New pages need to add material that does not fit the README; folders of
  link dumps will be declined.
- Do not invent numbers. Time estimates stay labelled as rough part-time estimates, and no repository,
  user, salary, hiring or outcome statistics are claimed anywhere. Certification costs stay described in
  words ("paid exam voucher") with a pointer to the vendor's current page, because fees change.

## Markdown gotchas

- URLs containing parentheses must be angle-bracketed: `<https://example.com/wiki/Foo_(bar)>`.
- Autolink external URLs (`<https://example.com>`) rather than bare text, so trailing punctuation is not
  absorbed into the link.
- Check in-tree anchors before you push: a heading's anchor is the lowercased heading with punctuation
  stripped and spaces replaced by hyphens.

## Sending a change

1. Describe the change and why it belongs in the roadmap.
2. Include your `curl` output (or the status code) for every link added or changed.
3. Open a pull request against `main`. Small, focused pull requests get reviewed faster.

## Reporting a broken link

Open an issue or a one-line pull request with the URL and the status code you saw. Broken links are
treated as bugs, not as trivia.

## License

By contributing, you agree that your contributions are licensed under the [MIT License](LICENSE).
