# Ishtehar — Free AI Ad-Creative Studio

**Live:** https://clinic-demo.fastapicloud.dev/ishtehar

Original clean-room build from the daily-app-gap-build series (2026-10-25).
Target studied from PUBLIC sources only: AdCreative.ai — a $39–$999/mo
credit-metered ad-creative platform whose 2026 credit cuts, card-required
trial, and billing/refund complaints are its biggest gaps.

## What Ishtehar does differently

1. **Free, unlimited, no account, no card, no credits.** Unlimited brands,
   unlimited variants, unlimited exports. The meter is removed entirely.
2. **Platform-correct by construction.** Every variant is validated against
   the platforms' real public limits (Meta primary 125 / headline 40 /
   description 30; Google RSA headline 30 / description 90; LinkedIn intro
   600 / headline 70; WhatsApp 1000) and hard-fit at a word boundary —
   nothing over the limit ever ships, and trimming is flagged.
3. **Transparent creative score.** 0–100 from documented, auditable rules:
   length fit 25, CTA 20, benefit 20, proof/number 15, emoji budget 10,
   hook/offer 10, minus 10 per compliance flag. No black-box "AI score".
4. **Compliance checker built in.** Flags guarantee claims, cure claims,
   unsubstantiated superlatives, income promises, "risk-free" and "100%
   safe" wording before they ship — the claim types that get ad accounts
   banned.
5. **Unlimited brands + 6 angles × 4 platforms** from one brief, in English
   and Roman-Urdu, with CSV/print export. Optional Gemini rewrite when the
   user has their own key (read from the environment at call time only).
6. **Honest scope.** It writes ad copy and creative briefs; it does not run
   campaigns, manage bids, or track ROAS — stated plainly, not upsold.

## Layout

- `engine.py` — platform specs, angle templates (EN + Roman-Urdu),
  word-boundary fitting, scorer, compliance rules, deterministic generator.
- `gemini.py` — optional AI rewrite (key at call time, never stored).
- `pages.py` — single-page UI; brand profiles in the user's localStorage.
- `routes.py` — FastAPI router (`/ishtehar`, `/api/build`,
  `/api/ai-rewrite`, `/api/download-csv`, `/api/platforms`,
  `/api/ai-status`).
- `tests/verify.py` — 48 checks, no network, no key needed.

## Verify

```text
python3 tests/verify.py
```

## Not affiliated

Not affiliated with AdCreative.ai or any other ad-creative tool. No
trademarked names, no copied creative, no decompiled code, no
license/paywall defeat — study-then-rebuild-original only.
