# WTFOOD Privacy Policy (Draft — Pending Legal Review)

*Last updated: [DATE]*

**This is a thorough working draft, not a finished legal document.** It has been written to accurately reflect what the WTFOOD app and backend actually do — verified directly against the source code, not assumed — and to address the specific GDPR and Google Play Data Safety obligations that apply to an app handling allergy/health-adjacent data. It still needs a qualified lawyer's review before publishing, particularly the items marked **[LEGAL REVIEW NEEDED]**, which involve judgment calls a document can't resolve on its own (data processing agreements, international transfer mechanisms, whether a DPO is required, breach notification procedures).

---

## 1. Who we are (the data controller)

WTFOOD ("we", "us", "our") is operated by **[Paul Dzamara], of **[Tuam, Galway, Ireland]**. Contact for privacy matters: **pauldzamara@gmail.com**.

**[LEGAL REVIEW NEEDED — EU representative]**: If the controller (you) is based outside the EU/EEA but WTFOOD is offered to users in the EU (which it is, per the app's EU/Ireland focus), GDPR Article 27 may require appointing an EU-based representative unless an exemption applies (e.g. only occasional processing, no large-scale special-category data processing, low risk to individuals). Given this app processes allergy data — which is special-category health data — at what could become meaningful scale, have a lawyer confirm whether Article 27 applies to you specifically.

**[LEGAL REVIEW NEEDED — Data Protection Officer]**: Article 37 requires a DPO where core activities involve large-scale, systematic processing of special-category data. WTFOOD isn't there at launch, but if it grows, this should be reassessed — worth a one-line note from your lawyer on what "large-scale" would mean for you.

## 2. What we collect, and why

This list matches what the app's backend code actually stores — not a generic template.

**Account information** (only if you create an account — using the app without an account is possible via anonymous/device-based usage):
- Email address and a hashed password (if you register with email/password — we never store your password in plain text; it's hashed using the Argon2 algorithm).
- Name and profile picture (if you sign in with Google — provided by Google, not collected independently).

**Allergy and dietary preferences**: the EU allergens and dietary preferences (e.g. vegan, gluten-free, limit preservatives) you choose to select, so the app can flag relevant ingredients for you specifically. **This is health-related data under GDPR Article 9** and is processed only with your explicit, freely-given consent — setting these preferences is entirely optional and the core scanning feature works without them.

**Scan history**: the products you've scanned and when, so you can revisit past results.

**Photos of ingredient labels**: when you use "Scan Ingredient Label," the photo is sent to our backend and forwarded to Anthropic's API purely to extract the printed text (OCR). **The photo itself is not stored by us at any point** — only the extracted text (the ingredient list) is saved to your account. The image exists only for the duration of that one request.

**Community submission photos**: if you submit a product suggestion (to help us add a product we don't have), we similarly **do not store the photos you take**. We store only the barcode, a timestamp, the review status, and a record of which photos you confirmed you provided — not the images themselves.

**Device identifier**: a locally-generated device ID, used so scan history and preferences work even before you create an account, and so we can later merge that history into your account if you sign up.

**Standard technical/server logs**: IP address and request metadata retained briefly by our hosting provider (Railway) for operational and security purposes (e.g. abuse prevention, rate limiting), not linked to a profile for any other purpose.

We do **not** collect: precise location, contacts, financial/payment information, or any data about children specifically (see Section 9).

## 3. Legal basis for processing (GDPR Article 6, and Article 9 for health data)

- **Allergy and dietary preference data**: your **explicit consent** (Article 9(2)(a)) — because this can reveal health-related information. You can decline to provide it, and you can withdraw consent at any time by clearing it in the app's Preferences screen, which deletes it immediately from that point forward.
- **Account data (email, name, password)**: necessary for performance of a contract — providing you the account-based features of the app (Article 6(1)(b)).
- **Scan history and device ID**: also contract performance (Article 6(1)(b)), and legitimate interest (Article 6(1)(f)) in providing a functional, personalized product — balanced against your right to have this deleted at any time.
- **Technical/security logs**: legitimate interest (Article 6(1)(f)) in keeping the service secure and reliable.

## 4. How ingredient/allergen data is used

Your allergy and dietary information is used **only** to power in-app alerts and personalization. It is not sold, not used for advertising (we don't show ads), and not shared with any third party except as strictly necessary to run the feature itself (see Section 5).

## 5. Third parties and processors

**[LEGAL REVIEW NEEDED]**: for each of these, confirm a Data Processing Agreement (DPA) is actually in place — most reputable providers offer a standard one, but it needs to be reviewed and executed, not assumed.

- **Anthropic** — receives ingredient-label photos transiently, solely to extract text via AI vision. Anthropic does not use API data to train its models by default under its API terms. Photos are not retained by Anthropic beyond generating the response, per their API data retention policy (confirm current terms at the time of publishing, as vendor policies do change).
- **Google** — if you sign in with Google, we verify your Google identity token to confirm who you are. We receive your name, email, and profile picture from Google for this purpose only.
- **Open Food Facts** — receives only the barcode number when you scan a product; no personal or account data is sent to them.
- **Railway** — hosts our backend server (API).
- **MongoDB Atlas** — hosts our database (accounts, preferences, scan history, submission records).

**[LEGAL REVIEW NEEDED — international transfers]**: Anthropic, Google, MongoDB Atlas, and Railway may process data on servers outside the EEA (commonly the US). Where that's the case, transfers need a valid mechanism under GDPR Chapter V — typically Standard Contractual Clauses (SCCs), which these providers generally offer as part of their standard DPA. This needs to be confirmed provider-by-provider rather than assumed, and disclosed here once confirmed (e.g. "we rely on Standard Contractual Clauses with [provider]").

## 6. Data retention and deletion

- **Allergy/diet preferences**: kept until you clear them (immediate) or delete your account.
- **Scan history**: kept while your account is active, deletable at any time.
- **Account deletion**: available in-app. When you delete your account, we immediately: revoke all active sessions, anonymize your email/name/profile picture so the account can no longer identify you, and mark your preferences, history, and other records as deleted so they no longer appear anywhere in the app.

**[LEGAL REVIEW NEEDED — "soft delete" vs. permanent erasure]**: technically, account deletion today anonymizes and flags records as deleted rather than immediately and permanently purging the underlying database rows. Once data is genuinely anonymized (no longer identifiable to you), it generally falls outside GDPR's definition of personal data, which is often sufficient to satisfy Article 17 (right to erasure) — but this is exactly the kind of determination that needs a lawyer's sign-off rather than a developer's assumption, and you may want a scheduled permanent-purge job on top of the anonymization step as a belt-and-braces measure.

## 7. Your rights under GDPR

You have the right to:
- **Access** the personal data we hold about you.
- **Rectify** inaccurate data.
- **Erase** your data ("right to be forgotten") — available directly in-app via account deletion, or by contacting us.
- **Restrict** or **object** to certain processing.
- **Data portability** — receive your data in a portable format.
- **Withdraw consent** at any time for anything processed on a consent basis (e.g. your allergy/diet preferences), without affecting the lawfulness of processing before withdrawal.
- **Lodge a complaint** with a supervisory authority — in Ireland, the Data Protection Commission (dataprotection.ie).

To exercise any of these rights beyond what's available in-app, contact **pauldzamara@gmail.com**.

## 8. Security

- All data in transit is encrypted (HTTPS/TLS) between the app, our backend, and every third party listed in Section 5.
- Passwords are never stored in plain text — they're hashed using Argon2.
- Ingredient-label photos are never persisted to our database, for either OCR scans or community submissions — reducing the amount of sensitive image data at risk in the first place.
- Access to production infrastructure (Railway, MongoDB Atlas) is restricted to [describe who/how — e.g. "the development team, via credentialed access only"].

**[LEGAL REVIEW NEEDED — breach notification]**: have a documented process ready for GDPR's 72-hour breach notification requirement (Article 33) before launch, even if you never need it.

## 9. Children

WTFOOD is not directed at children, and we do not knowingly collect personal data from children. The app's "Children's food mode" only changes how results are displayed (simpler language) — it does not collect any additional data, and does not create or require a separate account for a child.

**[LEGAL REVIEW NEEDED]**: GDPR's digital consent age varies by EU member state (13–16). If you have reason to believe the app attracts younger users, confirm your stated minimum age and any age-verification approach with a lawyer, and review this against Google Play's Families Policy if relevant.

## 10. Automated processing

WTFOOD uses your stated preferences to filter and highlight ingredient information — this is straightforward rule-based personalization, not automated decision-making that produces legal or similarly significant effects on you under GDPR Article 22. No profiling is used for advertising, since the app shows no ads.

## 11. Analytics and tracking

WTFOOD does not currently integrate any third-party analytics or advertising SDKs. If this changes in the future, this policy — and the app's Google Play Data Safety declaration — must be updated before that change ships, not after.

## 12. Changes to this policy

We will update this policy as the app evolves and notify users of material changes in-app (e.g. on next launch after a change takes effect).

## 13. Contact

**pauldzamara@gmail.com**

---

