# Store and platform rules for Memento

All sources read 2026-11-25. Every source is official (the store's or
vendor's own page) unless marked **secondary**. Quotes are copied from the
page text as served that day; "/" separates lines or table cells, "..."
marks words left out. Nothing here says Memento complies with a rule.

## 1. Google Play: SMS permission groups

Sources (official, read 2026-11-25):
- "Use of SMS or Call Log permission groups", Play Console Help,
  https://support.google.com/googleplay/android-developer/answer/10208820
- Preview of that article as updated for 2027,
  https://support.google.com/googleplay/android-developer/answer/17225965
- "Declare permissions for your app", Play Console Help,
  https://support.google.com/googleplay/android-developer/answer/9214102

Quoted words:
- Default handler: "Apps must be actively registered as the default SMS,
  Phone, or Assistant handler before prompting users to accept any of SMS or
  Call Log permissions. Those apps must immediately stop using the permission
  when they're no longer the default handler."
- Exceptions: "Google Play may provide a temporary exception to apps that
  aren't Default SMS, Phone, or Assistant handlers when:" / "Use of the
  permission enables the core app functionality listed in the following
  table and" / "there's currently no alternative method to provide the core
  functionality."
- The row that fits a tracker: "SMS-based money management" / "For example,
  apps that track and manage budget" / "READ_SMS, RECEIVE_MMS, RECEIVE_SMS,
  RECEIVE_WAP_PUSH", footnoted "Subject to Google Play review and approval."
- The payments row (not Memento's case): "SMS-based financial transactions"
  / "For example, Unified Payments Interface (UPI), verifications for
  financial transactions".
- "Only access Call Log or SMS permissions when your app falls within
  permitted uses and only to enable your app’s critical core functionality."
  and "Make sure that your app’s description prominently documents and
  promotes its core feature(s)."
- "If you believe your app meets the policy requirements for acceptable use
  or is eligible for an exception, you must declare any Call Log or SMS
  permissions directly through Google Play Console." and "Apps that fail to
  meet policy requirements or lack a Permissions Declaration Form may be
  removed from Google Play."
- "For example, personal loans or budgeting apps may not exfiltrate or share
  non-financial or personal SMS history of a user." and "User Data Policy
  Requirements - This includes Privacy Policy and Prominent Disclosure and
  Consent requirements."
- Invalid uses include "SMS or phone notification enhancement and alerts
  (when the app is not the default handler or an eligible exception)"; "This
  list is not exhaustive."
- Declare page: "You must specify your app's core functionality from the
  list of supported use cases."; "You must provide a video demonstration so
  the Google Play review team can easily evaluate your app's core
  functionality."; "Your request may require up to several weeks to
  process."
- The change announced "(effective January 27, 2027)" concerns READ_CALL_LOG
  only; the preview still lists "SMS-based money management" / "For example,
  apps that track and manage budget".

What it means for Memento (SMS capture, store listing): Memento is not the
default SMS app, so READ_SMS and RECEIVE_SMS on Play depend on Google
granting the "SMS-based money management" exception, case by case, after a
Permissions Declaration Form, a demo video and an extended review. RECEIVE_SMS
is in that row. SMS capture must be the core feature, promoted in the store
description.

Open: whether Google files a bank-alert transaction tracker under a row whose
only example is "apps that track and manage budget"; what "temporary" means
(how long, renewal, withdrawal); whether Google would see email capture or
manual entry as an "alternative method"; whether the split feature weighs on
the core-functionality judgement. Receiving SMS while the app is closed is not
discussed beyond RECEIVE_SMS being listed.

## 2. Google Play: Data safety section and privacy policy

Sources (official, read 2026-11-25):
- "Provide information for Google Play's Data safety section", Play Console
  Help, https://support.google.com/googleplay/android-developer/answer/10787469
  (latest dated revision on the page: December 5, 2023)
- "User Data", Play Console Help (policy),
  https://support.google.com/googleplay/android-developer/answer/10144311

Quoted words:
- "\"Collect\" means transmitting data from your app off a user’s device."
- "On-device access/processing: User data accessed by your app that is only
  processed locally on the user’s device and not sent off device does not
  need to be disclosed."
- "\"Sharing\" refers to transferring user data collected from your app to a
  third party." Not sharing: "Transferring user data to a third party based
  on a specific user-initiated action, where the user reasonably expects the
  data to be shared".
- "Even developers with apps that do not collect any user data must complete
  this form and provide a link to their privacy policy. In this case, the
  completed form and privacy policy can indicate that no user data is
  collected or shared."
- "Ensure that you've added a privacy policy; this is required to complete
  the Data safety form and have your data safety information shown to
  users."
- User Data policy: "All apps must post a privacy policy link in the
  designated field within Play Console, and a privacy policy link or text
  within the app itself." / "Apps that do not access any personal and
  sensitive user data must still submit a privacy policy." / "Please make
  sure your privacy policy is available on an active, publicly accessible and
  non-geofenced URL (no PDFs) and is non-editable."
- "Personal and sensitive user data includes, but isn't limited to,
  personally identifiable information, financial and payment information,
  authentication information, phonebook, contacts, device location, SMS and
  call-related data, ..."
- Prominent Disclosure & Consent: "In cases where your app's access,
  collection, use, or sharing of personal and sensitive user data may not be
  within the reasonable expectation of the user of the product or feature in
  question (for example, if data collection occurs in the background when the
  user is not engaging with your app), you must meet the following
  requirements:" ... "Requests for in-app user consent and runtime permission
  requests must be immediately preceded by an in-app disclosure that meets
  the requirement of this policy."

What it means for Memento (privacy policy, store listing, SMS capture): a
privacy policy is required, at a public URL and inside the app, although
nothing leaves the phone. Data processed only on the phone need not be
declared as collected, but the form must still be filled in. Background SMS
reading is the kind of case the in-app disclosure before the permission
request is written for.

Open: whether the app password and mail traffic Memento sends to the user's
own mail provider counts as "collect" (the definition does not say whether
data sent to a third party the user chose, never to the developer, is
covered); whether reviewers treat background SMS reading as outside
"reasonable expectation" when it is the app's core feature.

## 3. Google Play: Financial features declaration

Sources (official, read 2026-11-25):
- "Provide information for the Financial features declaration", Play Console
  Help, https://support.google.com/googleplay/android-developer/answer/13849271
- "Financial Services", Play Console Help (policy),
  https://support.google.com/googleplay/android-developer/answer/9876821

Quoted words:
- "All developers that have an app published on Google Play must complete the
  Financial features declaration, including apps on closed testing, open
  testing, or production tracks."
- "Even developers with apps that do not offer any financial features must
  complete this form and certify that no financial features are offered
  through the app."
- The list's last group: "Support services" / "Credit monitoring and
  reporting" / "Financial advice" / "Insurance" / "Other". And: "If their
  app(s) don’t provide any financial features, developers must declare:" /
  "My app doesn’t provide any financial features".
- Documents are asked only for loans: "If your app includes personal
  loan-related features ... you’re required to upload further
  documentation."
- Financial Services policy: "For the purposes of this policy, we consider
  financial products and services to be those related to the management or
  investment of money and cryptocurrencies, including personalized advice."

What it means for Memento (store listing): the declaration is required either
way. Its list has no entry for expense tracking or budgeting; the choice is
between "Other" and "My app doesn’t provide any financial features".

Open: which applies to a tracker that makes no payments and gives no loans.
The policy's definition ("related to the management ... of money") may cover
budgeting; the pages do not say. This also bears on the account type
(section 4).

## 4. Google Play: publishing as an individual

Sources (official, read 2026-11-25):
- "App testing requirements for new personal developer accounts", Play
  Console Help, https://support.google.com/googleplay/android-developer/answer/14151465
- "Choose a developer account type", Play Console Help,
  https://support.google.com/googleplay/android-developer/answer/13634885
- "Play Console Requirements", Play Console Help (policy),
  https://support.google.com/googleplay/android-developer/answer/10788890

Quoted words:
- "Developers with personal accounts created after November 13, 2023, must
  run a closed test for their app with a minimum of 12 testers who have been
  opted in continuously for at least 14 days. When you meet these criteria,
  you can apply for production access on the Dashboard in Play Console to
  distribute your app on Google Play."
- "Choose a personal account if your account is for personal use—for
  example, if you're a student, hobbyist, or amateur developer."
- "You must choose an organization account if you provide any of the
  following services:" / "Financial products and services, including
  banking, loans, stock trading, investment funds, cryptocurrency software
  wallets, and cryptocurrency exchanges."
- "To create a developer account for an organization, you must provide a
  D-U-N-S number." and "Applying for a D-U-N-S number through Dun &
  Bradstreet is a completely free process."
- Requirements policy: "1.1. Financial products and services, including but
  not limited to banking, loans, stock trading, investment funds,
  cryptocurrency software wallets, and cryptocurrency exchanges." and
  "Verified information will be shown on Google Play to help users build
  trust and confidence with developers."

What it means for Memento (publishing as an individual): a personal account
needs a closed test with at least 12 testers opted in for 14 days in a row
before production. If Google counts an expense tracker as "financial
products and services", it cannot be published from a personal account; an
organization account needs a D-U-N-S number.

Open: whether a tracker with no payments, loans or advice is a "financial
product or service" here. The listed examples all handle money, but the
policy says "including but not limited to" and the Financial Services
definition covers "management ... of money". Which personal-account details
Play shows publicly is on a linked page not read here.

## 5. Android developer verification

Sources (official, read 2026-11-25):
- "Android developer verification", https://developer.android.com/developer-verification
- Its guides under https://developer.android.com/developer-verification/guides
  (overview, google-play-console, limited-distribution, full-distribution,
  open-source-app-registration, faq)

Quoted words:
- "Android requires all apps to be registered by verified developers for
  users to install them on certified Android devices."
- Timeline: "August 2026" / "Developer APIs, limited distribution accounts,
  and power user advanced flow launch." / "September 30, 2026" / "Protections
  begin for all users who install apps from participating stores in Brazil,
  Indonesia, Singapore, and Thailand on certified devices running Android 8
  (API level 26) or higher." / "2027 and beyond" / "Verification capability
  will be expanded globally for all apps on certified Android devices in
  2027."
- Play: "Google Play automatically registers 99% of apps." and "For most Play
  developers, no new action is required for identity verification." and "For
  new apps, when you create an app in the Google Play Console, Google Play
  automatically registers the package name and links it to your account."
- Outside Play, full distribution: "Individuals must submit a
  government-issued photo ID and proof of address document as part of the
  verification program." FAQ: "The $25 fee for the Full Distribution account
  in the ADC helps cover administrative costs ..."
- Limited distribution guide: "Share apps with up to 50 devices that
  end-users have explicitly authorized." / "This account is free." / "you
  don't need to provide a government ID". The landing page and FAQ say
  "share apps with up to 20 devices" and "up to 20 specific devices".
- "As a developer, you are free to install apps without verification with
  ADB." (FAQ, last updated September 3, 2025)
- Unregistered apps: "users can enable advanced flow on their device. This
  one-time setup allows them to install apps from unverified developers."

What it means for Memento (publishing as an individual): on Play, the package
is registered when the app is created in Play Console. The developer's own
builds installed with ADB need nothing. APKs given to people in India outside
Play will need a registered package (full distribution: ID, proof of address,
$25; or free limited distribution to a capped number of devices) once
enforcement reaches India, or those users must turn on the advanced flow.

Open: no India date beyond "globally ... in 2027"; the limited distribution
device cap (Google's pages say both 20 and 50).

## 6. Apple App Review Guidelines (iOS later)

Source (official, read 2026-11-25): "App Review Guidelines", Apple Developer,
https://developer.apple.com/app-store/review/guidelines/ (page shows "Last
Updated: October 16, 2026").

Quoted words:
- 5.1.1(i): "Privacy Policies: All apps must include a link to their privacy
  policy in the App Store Connect metadata field and within the app in an
  easily accessible manner. The privacy policy must clearly and explicitly:"
  / "Identify what data, if any, the app/service collects, how it collects
  that data, and all uses of that data." / "Explain its data
  retention/deletion policies and describe how a user can revoke consent
  and/or request deletion of the user’s data."
- 5.1.1(ix): "Apps that provide services in highly regulated fields (such as
  banking and financial services, healthcare, gambling, legal cannabis use,
  air travel and crypto exchanges) or that require sensitive user information
  should be submitted by a legal entity that provides the services, and not
  by an individual developer."

What it means for Memento (iOS later, privacy policy, publishing as an
individual): an iOS version needs a privacy policy link in App Store Connect
and in the app. If Apple reads Memento as "financial services" or as
requiring "sensitive user information", 5.1.1(ix) says a legal entity, not an
individual, should submit it.

Open: whether a local-only tracker of the user's own transactions falls under
5.1.1(ix); the rule says "should" and gives no test for trackers. Whether iOS
lets an app read SMS at all is not a review-guideline question and was not
researched.

## 7. Google app passwords (email capture, first route)

Sources (official, read 2026-11-25):
- "Sign in with app passwords", Google Account Help,
  https://support.google.com/accounts/answer/185833
- "Add Gmail to another email client", Gmail Help,
  https://support.google.com/mail/answer/7126229
- "Transition from less secure apps to OAuth", Google Workspace Help,
  https://support.google.com/a/answer/14114704 (redirects to
  knowledge.workspace.google.com; "Last updated 2026-11-10 UTC")

Quoted words:
- "App passwords aren't recommended and are unnecessary in most cases. To
  help keep your account secure, use \"Sign in with Google\" to connect apps
  to your Google Account."
- "An app password is a 16-digit passcode that gives a less secure app or
  device permission to access your Google Account. App passwords can only be
  used with accounts that have 2-Step Verification turned on."
- "If you've set up 2-Step Verification but can't find the option to add an
  app password, it might be because:" / "Your Google Account has 2-Step
  Verification set up only for security keys." / "You're logged into a work,
  school, or another organization account." / "Your Google Account has
  Advanced Protection."
- "To help protect your account, we revoke your app passwords when you change
  your Google Account password."
- Gmail Help: "To keep your account more secure, Gmail no longer supports
  third-party apps or devices which require you to share your Google username
  and password." and "Use an app password. If you use 2-Step Verification,
  try signing in with an app password." and "IMAP access is always turned on
  in Gmail".
- Workspace: "You will no longer use a password for access (with the
  exception of app passwords)." and "CalDAV, CardDAV, IMAP, SMTP, and POP
  will no longer work with legacy passwords (basic authentication)."

What it means for Memento (email capture): Google still describes IMAP with
an app password as working, but only with 2-Step Verification, and not for
work or school accounts, security-key-only 2SV or Advanced Protection. Google
discourages it, and a password change revokes it, so the app needs a path for
a rejected password.

Open: no removal of app passwords was found on Google's own pages (Account,
Gmail and Workspace Help, and a search of the Workspace Updates blog).
Search results listed third-party blogs (**secondary**, not read, not relied
on) claiming a phase-out; none of the snippets cited a Google announcement.
No announcement is not a promise that app passwords stay.

## 8. Gmail API restricted scopes (possible later route)

Sources (official, read 2026-11-25):
- "Choose Gmail API scopes",
  https://developers.google.com/workspace/gmail/api/auth/scopes ("Last
  updated 2026-09-10 UTC")
- "Restricted scope verification",
  https://developers.google.com/identity/protocols/oauth2/production-readiness/restricted-scope-verification
  ("Last updated 2026-11-10 UTC")
- "Security Assessment", https://support.google.com/cloud/answer/13465431
- "When is verification not needed",
  https://support.google.com/cloud/answer/13464323
- "Google Workspace user data and developer policy",
  https://developers.google.com/workspace/workspace-api-user-data-developer-policy
  ("Last updated 2026-09-03 UTC")

Quoted words:
- Under "Restricted scopes": "https://www.googleapis.com/auth/gmail.readonly"
  / "View your email messages and settings." Definition: "Restricted: These
  scopes provide wide access to Google user data and require restricted scope
  OAuth App Verification." and "If you store restricted scope data on servers
  (or transmit), then you must go through a security assessment."
- These scopes "require you to go through a scope verification process before
  you request the scopes from any Google Account".
- Developers page: "Every app that requests access to Google users'
  restricted data and has the ability to access data from or through a
  third-party server must go through a security assessment from
  Google-empanelled security assessors." and "complete a security assessment
  at least every 12 months after your assessor's Letter of Assessment (LOA)
  approval date."
- Cloud Help page: "applications requesting access to restricted scopes must
  undergo an annual security assessment." and "All applications must be
  revalidated every year."
- Exemptions (Cloud Help): "Personal mode apps: If you are the only user of
  your app, ... Personal mode apps are restricted exclusively to the
  creator's Google Account, do not require verification, and do not display
  the \"unverified app\" warning screen." and "Limited Audience apps: If the
  app is intended for a limited audience (fewer than 100 users), you and your
  limited number of users can continue using the app without going through
  verification(users will be allowed to click through “unverified app”
  warning screens during sign-in). Such apps will need to complete a
  verification, if they want to grow their user base beyond 100."
- Approved Gmail use cases include "Applications that use information from
  emails to provide reporting or monitoring services for the benefit of users
  that improve the email experience (such as applications that automate
  travel itineraries or track flights or package delivery statuses)".

What it means for Memento (email capture, later): a public Gmail OAuth route
needs restricted-scope verification. For the developer's own use, Personal
mode, or a limited audience under 100 users, needs none.

Open: whether an app that reads Gmail only on the phone, with no server,
needs the yearly security assessment: the developers page ties it to a
"third-party server", the Cloud Help page says all restricted-scope apps.
Whether reading bank alerts to record transactions fits an approved use case
(nearest: "reporting or monitoring services ... that improve the email
experience"). How the 100-user cap applies to an open source app whose users
share one OAuth client.

## 9. Outlook.com: IMAP with a password

Sources (official, read 2026-11-25):
- "POP, IMAP, and SMTP settings for Outlook.com", Microsoft Support,
  https://support.microsoft.com/en-us/office/pop-imap-and-smtp-settings-for-outlook-com-d088b986-291d-42b8-9564-9c414e2aa040
- "Modern Authentication Methods now needed to continue syncing Outlook Email
  in non-Microsoft email apps", Microsoft Support (Last Updated: June 10,
  2024),
  https://support.microsoft.com/en-gb/office/modern-authentication-methods-now-needed-to-continue-syncing-outlook-email-in-non-microsoft-email-apps-c5d65390-9676-4763-b41f-d7986499a90d

Quoted words:
- Settings page: "Outlook.com requires the use of Modern Auth / OAuth2."; the
  IMAP rows give "Authentication Method" / "OAuth2/Modern Auth"; the same
  page also gives "Password" / "Your Microsoft account password." / "If your
  password is not being recognized, or if you want to add your Outlook.com
  account to a smart device like a home security camera, you may need an app
  password."
- "POP & IMAP access is disabled by default."
- Notice: "September 16th, 2024" / "Basic Authentication no longer available
  to access any Outlook account" and "After September 16th, users attempting
  to connect their Microsoft accounts through Basic Authentication will fail
  to do so."

What it means for Memento (email capture): Microsoft's pages say IMAP to
Outlook.com needs OAuth2 and that password (Basic) sign-in ended on
September 16, 2024, so IMAP with a password should not be expected to work
for Outlook.com accounts. The user must also turn IMAP on first.

Open: whether an Outlook.com app password still works over IMAP (the
settings page mentions one and also requires OAuth2). Microsoft's terms for
an app using OAuth2 with Outlook.com were not researched.

## 10. Developer fees

Sources (official, read 2026-11-25):
- "Get started with Play Console", Play Console Help,
  https://support.google.com/googleplay/android-developer/answer/6112435
- "Enrollment", Apple Developer Support,
  https://developer.apple.com/support/enrollment/

Quoted words:
- Play: "There is a US$25 one-time registration fee." and "Google may require
  a valid government ID and a credit card, both issued under your legal
  name."
- Apple: "The Apple Developer Program annual fee is 99 USD and the Apple
  Developer Enterprise Program annual fee is 299 USD, in local currency where
  available."

What it means for Memento (publishing, cost): a Play developer account costs
US$25 once; an App Store release costs 99 USD a year.

## Not verified

- Whether Google would grant Memento the "SMS-based money management"
  exception: only a declaration and review settle it.
- Whether an expense tracker is "financial products and services" on Play
  (organization account, D-U-N-S), or falls under Apple 5.1.1(ix).
- Whether Memento declares "Other" or "My app doesn’t provide any financial
  features".
- Whether an on-phone-only Gmail OAuth app needs the yearly security
  assessment (Google's pages conflict), and whether it fits an approved use.
- Any Google announcement removing app passwords: none found on Google's own
  pages; third-party claims (**secondary**) not read.
- Whether Outlook.com app passwords work with IMAP: Microsoft's pages
  conflict; not tested.
- Android developer verification: no India date; limited distribution cap
  given as both 20 and 50 devices.
- Which personal-account details Play shows publicly: linked page not read.
- Whether iOS offers any way to read SMS: outside these rules, not
  researched.
