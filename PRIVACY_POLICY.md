# WTFOOD Privacy Policy

*Last updated: September 13, 2026*

This policy explains what information WTFOOD collects, why, and how you can control it.

## 1. Who we are

WTFOOD ("we", "us", "our") is operated by **Paul Dzamara**, of **Tuam, Galway, Ireland**. Contact for privacy matters: **pauldzamara@gmail.com**.

## 2. What we collect, and why

**Account information** (only if you create an account — the app can also be used anonymously via a device identifier):
- Email address and a hashed password, if you register with email/password. We never store your password in plain text — it's hashed using the Argon2 algorithm.
- Name and profile picture, if you sign in with Google (provided by Google, not collected independently).

**Allergy and dietary preferences**: the allergens and dietary preferences you choose to select, so the app can flag relevant ingredients specifically for you. This is health-related data under GDPR Article 9, and is processed only with your explicit, freely-given consent — setting these preferences is entirely optional, and the core scanning feature works without them.

**Scan history**: the products you've scanned and when, so you can revisit past results.

**Photos of ingredient labels**: when you use "Scan Ingredient Label," the photo is sent to our backend and forwarded to Anthropic's API purely to extract the printed text (OCR). The photo itself is not stored by us at any point — only the extracted text is saved to your account. The image exists only for the duration of that one request.

**Community submission photos**: if you submit a product suggestion to help us add a product we don't have, we similarly do not store the photos you take. We store only the barcode, a timestamp, the review status, and a record of which photos you confirmed you provided — not the images themselves.

**Device identifier**: a locally-generated device ID, used so scan history and preferences work even before you create an account, and so that history can later be linked to your account if you sign up.

**Standard technical/server logs**: IP address and request metadata, retained briefly by our hosting provider for operational and security purposes (e.g. abuse prevention, rate limiting), not used for any other purpose.

We do **not** collect precise location, contacts, financial/payment information, or any data specifically about children.

## 3. Legal basis for processing

- **Allergy and dietary preference data**: your explicit consent (GDPR Article 9(2)(a)), since this can reveal health-related information. You can decline to provide it, and withdraw consent at any time by clearing it in the app's Preferences screen, which deletes it immediately.
- **Account data** (email, name, password): necessary to provide the account-based features of the app (Article 6(1)(b)).
- **Scan history and device ID**: contract performance and our legitimate interest in providing a functional, personalized product (Article 6(1)(b) and (f)), balanced against your right to have this deleted at any time.
- **Technical/security logs**: our legitimate interest in keeping the service secure and reliable (Article 6(1)(f)).

## 4. How allergy and ingredient data is used

Your allergy and dietary information is used only to power in-app alerts and personalization. It is not sold, not used for advertising — we show no ads — and not shared with any third party except as strictly necessary to run the feature itself (see Section 5).

## 5. Third parties

- **Anthropic** — receives ingredient-label photos transiently, solely to extract text via AI vision. Photos are not retained beyond generating that response.
- **Google** — if you sign in with Google, we verify your Google identity token to confirm who you are, receiving your name, email, and profile picture for this purpose only.
- **Open Food Facts** — receives only the barcode number when you scan a product; no personal or account data is sent.
- **Railway** — hosts our backend server.
- **MongoDB Atlas** — hosts our database.

We require our service providers to handle data in accordance with applicable data protection law, including appropriate safeguards for any transfers outside the EEA, such as Standard Contractual Clauses where applicable.

## 6. Data retention and deletion

- **Allergy/diet preferences**: kept until you clear them (immediate) or delete your account.
- **Scan history**: kept while your account is active, deletable at any time.
- **Account deletion**: available directly in the app. When you delete your account, we immediately revoke all active sessions, anonymize your email, name, and profile picture so the account can no longer identify you, and mark your preferences, history, and other records as deleted so they no longer appear anywhere in the app.

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
- Ingredient-label photos are never persisted to our database, for either OCR scans or community submissions.
- Access to production infrastructure is restricted to the development team, via credentialed access only.
- In the unlikely event of a data breach, we will notify affected users and the relevant supervisory authority as required by law.

## 9. Children

WTFOOD is not directed at children, and we do not knowingly collect personal data from children. The app's "Children's food mode" only changes how results are displayed (simpler language) — it does not collect any additional data, and does not create or require a separate account for a child.

## 10. Automated processing

WTFOOD uses your stated preferences to filter and highlight ingredient information — this is rule-based personalization, not automated decision-making that produces legal or similarly significant effects on you under GDPR Article 22. No profiling is used for advertising, since the app shows no ads.

## 11. Analytics and tracking

WTFOOD does not currently integrate any third-party analytics or advertising SDKs. If this changes, this policy will be updated before that change takes effect.

## 12. Changes to this policy

We will update this policy as the app evolves and notify users of material changes in-app.

## 13. Contact

**pauldzamara@gmail.com**
