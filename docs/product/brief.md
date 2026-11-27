# Memento

Memento is an open source, privacy-first personal finance app, starting with
Android and India, for people whose money moves through several bank
accounts, cards and UPI. It records each payment in and out from the bank's
SMS and email alerts as it arrives, asks what the payment was for while the
user still remembers, splits shared expenses with friends, and shows
spending against a plan of where the money should go. In its local-only
build, everything stays on the phone. Of the more than 20 products surveyed,
the established Indian apps that capture payments automatically keep the
data on their own servers. Of those whose features the survey could check,
none describes a prompt at the moment of spending, and the only one that
both captures automatically and splits bills with friends is closed source,
paid, and declares that it collects SMS. The nearest open source apps the
survey found appeared in October 2026. Its first user is its owner, who
builds it for their own money.

## Problem

Money moves through many channels: several bank accounts, credit and debit
cards, UPI. Nothing shows in one place what came in and what went out. In
October 2026, India made about 25.47 billion UPI payments
([survey](../research/existing-products.md#how-fragmented-an-indian-users-money-is)).

The owner's salary is gone about two weeks after it is credited, through
card bills, EMIs and everyday payments, and the owner can't say what it went
on. Finding out means reading statements months later, when the payments
can no longer be remembered, so there is nothing to plan the next month
from. A friend paying back, a refund, a transfer between the owner's own
accounts or a card bill payment is neither spending nor income, and counting
it as one gives the wrong picture. Shared expenses the owner pays for
friends reach Splitwise months late, when nobody remembers the details.

## Users

Memento is for its owner first: someone in India with an Android phone,
several bank accounts, credit and debit cards and UPI, who pays for friends
and is paid back, and who wants to know where the money went and to plan
where it goes next. Then for others like them, once it is on Google Play.

They need:
- nothing to type for a payment their bank has already reported;
- to be asked about a payment while they still remember it;
- one list in which each payment appears once, and a transfer is not
  spending;
- a budget to spend against;
- shared expenses split on the day, and settled up in any amounts.

It is not for:
- **iPhone users, at first.** iOS gives apps no access to SMS
  ([ADR 1](../adr/0001-flutter-with-a-pure-dart-core.md)), so an iPhone
  version relies on email alerts, statements and typed entries, and comes
  after Android.
- **People outside India, at first.** The alerts it reads, and the rules it
  works within, are Indian banks'.
- **Anyone who wants their bank linked to the app, or the app to make
  payments.**

## What exists already

The [survey](../research/existing-products.md) read more than 20 products
and projects on 2026-11-25. Of those whose features it could check, none
meets the need in full.

- **Indian apps that capture automatically.** axio (formerly Walnut) reads
  bank SMS; Fold, Jupiter and CRED connect through the Account Aggregator
  framework, and INDmoney through linked accounts. They capture without
  typing, and axio has done it longest. Each keeps the data on its own
  servers, axio, INDmoney and CRED declare on Google Play that they collect
  SMS, and they are paid for by loans, credit cards, investing or, for Fold,
  a subscription.
- **Private apps that capture automatically.** Bluecoins reads bank SMS and
  banking apps' notifications and keeps the data on the phone, but reads no
  email and doesn't split with friends. FinArt reads SMS, email and
  notifications and splits group bills, but is paid by subscription, and
  its Play declaration says it collects SMS for analytics. Both are closed
  source.
- **Small private trackers on Google Play.** PaisaSync, Vrid, TrakFi and
  AuraSpend are Indian SMS trackers whose listings say the data stays on the
  phone, and PaisaSync declares that it collects no data. What they do
  beyond their listings, such as splitting or a prompt at the moment of
  spending, was not checked.
- **Splitting apps.** Splitwise, Splid and Tricount handle groups, balances
  and settling up well, but every expense is typed in, and they keep no
  budget.
- **Budgeting apps.** Money Manager, YNAB and Goodbudget are built around
  budgets, and Wallet around bank sync, but each entry is typed in or comes
  from a bank sync, and YNAB's and Goodbudget's syncs cover no Indian
  bank.
- **Open source finance apps.** Cashew, Actual Budget and Firefly III are
  mature and keep the data with the user, but none reads Indian bank alerts
  as its main way in.
- **New open source apps for Indian bank alerts.** pckt reads SMS and email
  on the phone, merges duplicates, keeps transfers between the user's own
  accounts out of spending, and has budgets. Kosh reads SMS from Indian
  banks, imports statements and offers a daily digest notification, with a
  build that has no internet access.
  Both appeared in October 2026 under GPL-3.0, are installed from GitHub
  rather than Google Play, and neither describes a prompt at the moment of
  spending or splitting a bill with friends.

Of the products whose features the survey could check, none describes a
prompt at the moment of spending, and the only one that both captures
automatically and splits bills with friends is FinArt, which is closed,
paid, and declares that it collects SMS.

## Goals

- **Nothing to type.** Money in and out is recorded from bank SMS and email
  alerts as they arrive, and a statement fills in what had no alert.
- **Asked while they remember.** Within seconds of an SMS alert, a
  notification asks what the payment was for, with one tap to add a note, a
  category or a split. Email alerts are fetched from time to time rather
  than pushed, so their prompt comes later. A daily notification lists the
  payments still without a note or category, and a user who wants only that
  can switch the instant one off.
- **Each payment once.** When an SMS, an email and a statement line report
  the same payment, it is recorded once.
- **A true picture.** Transfers between the user's own accounts, credit card
  bill payments, refunds and friends paying back are not counted as
  spending or income, and failed or declined payments are not recorded.
- **A plan to spend against.** The user sets a budget for each category of
  spending for the month, sees what has been spent against it as payments
  arrive, and is warned as a budget runs out.
- **Splitting built in.** Any payment can be split with friends, kept in the
  app as names only the user sees. Balances are tracked, and settling up
  can be for any amount.
- **Private.** In the local-only build, everything stays on the phone: raw
  messages, payments, accounts, budgets and splits.
- **Later, splits shared with friends.** An optional cloud build lets
  friends who also use Memento see the splits they are in, and settle up
  with each other. It is the only build with a server.

## Not a goal

- **Guaranteed completeness.** Memento doesn't promise to catch every
  payment, or to keep balances exactly in step with the bank: banks decide
  which alerts they send. The raw text of every alert is kept, so a payment
  can be recorded again, or checked against the bank, without collecting
  anything again.
- **Linking bank accounts.** Memento doesn't fetch data from banks. The
  Account Aggregator framework is open only to entities a financial
  regulator registers
  ([Indian law](../research/indian-law.md#3-rbi-account-aggregator-framework)),
  so the data comes from the alerts the user already receives.
- **Moving money.** Memento records payments. It doesn't make them, lend or
  give advice.

## Success criteria

After a month of the owner's own use:
- at least 90% of the month's payments are recorded without typing, checked
  by hand against that month's bank and card statements;
- every shared expense is split within a day of the payment;
- every payment has a category within a day of being recorded, and the owner
  has set the next month's budgets in Memento before it starts.

## Cost and business model

- **Time:** the owner's, building alone with agents doing most of the work.
- **Services:** none for the local-only build. It has no server, and reads
  mail from the user's own mailbox.
- **Store fees:** a Google Play developer account costs US$25 once. An
  organization account, if Google requires one (see the second risk below),
  also needs a D-U-N-S number, which is free. An App Store release, for the
  iPhone version, costs 99 USD a year
  ([fees](../research/store-and-platform-rules.md#10-developer-fees)).
- **Avoided:** Gmail read through Google's sign-in would need Google's
  verification for a public release, and possibly a yearly security
  assessment by an assessor Google approves. Reading mail over IMAP with an
  app password needs neither.
- **The cloud build** adds the cost of running a server, which the change
  that adds it estimates.
- **Paid for by** the owner.

## Constraints

Each rule is quoted, with the date it was read, in the research note it
links. Nothing here says that Memento complies with a rule.

### Outside rules

| Rule | What it asks | What it governs |
|---|---|---|
| [Google Play: SMS permissions](../research/store-and-platform-rules.md#1-google-play-sms-permission-groups) | Google's temporary "SMS-based money management" exception, after a declaration, a demo video and a review of up to several weeks. SMS capture must be the core feature, promoted in the listing, and the app may not share a user's non-financial SMS. | SMS capture |
| [Google Play: user data](../research/store-and-platform-rules.md#2-google-play-data-safety-section-and-privacy-policy) | A public privacy policy, linked in the app; the Data safety form; a disclosure in the app before access the user may not expect, such as in the background. | The store listing and the app |
| [Google Play: financial features](../research/store-and-platform-rules.md#3-google-play-financial-features-declaration) | Every app declares its financial features; the list has no entry for tracking. | The store listing |
| [Google Play: developer accounts](../research/store-and-platform-rules.md#4-google-play-publishing-as-an-individual) | For a personal account created after 13 November 2023, a closed test with at least 12 testers for 14 days; an organization account for "Financial products and services". | Publishing |
| [Android developer verification](../research/store-and-platform-rules.md#5-android-developer-verification) | "Globally ... in 2027", with no date for India: a registered developer for apps installed from outside Google Play, apart from ADB installs and the user's advanced flow. | Builds outside Google Play |
| [Google app passwords](../research/store-and-platform-rules.md#7-google-app-passwords-email-capture-first-route) | 2-Step Verification, and the option may be missing, such as on work or school accounts. Google discourages them, and revokes them when the password changes. | Email capture |
| [Gmail API](../research/store-and-platform-rules.md#8-gmail-api-restricted-scopes-possible-later-route) | Google's verification for a public release, but not for the developer's own use or fewer than 100 users. | A later email route |
| [Outlook.com](../research/store-and-platform-rules.md#9-outlookcom-imap-with-a-password) | OAuth2 for IMAP. | Email capture |
| [Apple: guideline 5.1.1](../research/store-and-platform-rules.md#6-apple-app-review-guidelines-ios-later) | A privacy policy link. Apps in "banking and financial services", or "that require sensitive user information", "should be submitted by a legal entity". | The iPhone version |
| [India's data protection act](../research/indian-law.md#1-digital-personal-data-protection-act-2023-definitions-and-section-3) | It doesn't apply to data an individual processes "for any personal or domestic purpose". | All personal data |
| [DPDP Rules, 2025](../research/indian-law.md#2-digital-personal-data-protection-rules-2025-notification-and-commencement) | A Data Fiduciary's duties, from about May 2027. | The cloud build's server, and the app too if its developer is a Data Fiduciary (open below) |
| [RBI: Account Aggregators](../research/indian-law.md#3-rbi-account-aggregator-framework) | Through the Account Aggregator network, only regulated entities receive users' bank data. | Why capture reads alerts |
| [RBI: transaction alerts](../research/indian-law.md#4-rbi-banks-sms-alerts-for-electronic-transactions) | From 1 January 2027, commercial banks must send an SMS for each electronic banking transaction over ₹500, and decide for themselves at or below it; and an email for each one, where the customer gave an address. | SMS and email capture |
| [TRAI: SMS headers](../research/indian-law.md#5-trai-commercial-sms-headers-dlt-and-suffixes) | Commercial SMS come from registered headers marked by type, which doesn't prove the sender. | Recognising alerts |

**Open,** for the owner, who may put a question to a lawyer:
- whether Google grants Memento the SMS exception: the first risk below;
- whether Google Play counts a tracker that moves no money as a financial
  service, and whether Apple's guideline 5.1.1(ix) covers it as one, or as
  an app that requires sensitive user information: the second risk below;
- whether Memento declares "Other" or no financial features;
- whether a Gmail route with no server also needs Google's yearly security
  assessment, on which Google's pages disagree;
- whether writing an app that runs only on the user's phone makes the
  developer a "Data Fiduciary", and how the act applies to the cloud
  build's server;
- whether every UPI payment is an "electronic banking transaction" under
  RBI's rules;
- the alert rules for banks other than commercial banks, which were not
  read.

### Licences

Memento is licensed AGPL-3.0-or-later. Proposed for the owner's decision,
it takes in code under MIT, BSD-2-Clause, BSD-3-Clause, Apache-2.0, ISC,
Zlib, MPL-2.0 unless marked "Incompatible With Secondary Licenses", and
public domain dedications: SQLite's (`blessing`), Unlicense and CC0-1.0. It
takes in no GPL, LGPL or AGPL code from others: the FSF reads Apple's App
Store terms as incompatible with the GPL and AGPL, and a post on its blog
says the same of the LGPL, which would tie an iPhone release to those
authors' permission. Flutter (BSD-3-Clause), drift (MIT) and SQLite
fit ([licences](../research/licences.md)).

**Open:** whether Memento's own AGPL code can ship through the App Store,
with a permission its sole author adds, which no FSF source read says;
whether Google Play's terms clash with copyleft once the project has many
authors, as a 2012 FSF blog post says; and whether MPL-2.0 code can ship
through the App Store. Apple's and Google's current terms were not read.

### Security

- **The phone holds the user's whole money history,** with the raw text of
  their bank alerts.
- **A Gmail app password opens the whole mailbox,** not only bank alerts, so
  it is stored encrypted, with a key the phone's keystore holds, and kept out
  of backups.
- **An email's sender is easier to forge than an SMS header,** so an email
  alert is trusted only once its sender is checked.
- **The local-only build connects only to the user's own mail server.**
- **Real bank messages are personal data.** They are never committed or
  posted, and tests use anonymised copies.

### Personal data and where it goes

| Data | What it is for | Where it is kept |
|---|---|---|
| Raw SMS, emails and statements | Recording payments, and recording them again when a parser improves | The phone |
| Payments, accounts, notes, categories and budgets | The user's own record and plan | The phone |
| Friends' names, splits and settlements | Splitting and settling up | The phone |
| Mail address and app password | Fetching email alerts | The phone, encrypted, out of backups |

The cloud build's server holds the shared split and settlement records and
the sign-in of the people in them, each visible to the people in that
split. The change that adds it sets their fields, and updates this table.

## Assumptions and risks

Riskiest first, each with the cheapest way to check it.

1. **Google grants the SMS exception.** If it doesn't, the Play version
   can't read SMS, and capture rests on email, statements and typing.
   Several Indian SMS trackers are on Google Play: axio, which calls itself
   "an SMS-based money management app" and also uses the SMS permission
   for loan fraud checks, and small ones such as PaisaSync. Whether
   Memento is granted the exception, only its declaration settles. Check:
   submit the Permissions Declaration Form with the first closed-test
   build, weeks before a public release.
2. **An individual may publish it.** If Google counts a tracker as a
   "financial product or service", Google Play needs an organization
   account with a D-U-N-S number, and Apple's 5.1.1(ix) asks the same of
   the iPhone version. Check: ask Play Console support before registering
   the developer account.
3. **Alerts are enough to reach 90%.** From 1 January 2027, commercial
   banks may stop SMS for payments of ₹500 or less, and HDFC Bank already
   stopped SMS for small UPI payments in 2024, by a press report. Email
   alerts stay required wherever the customer gave an email address, so a
   bank that stops small SMS leaves the first success criterion resting on
   email capture. Check: count one month of the owner's payments against the SMS
   and emails received, now and again in January 2027.
4. **App passwords keep working.** Google discourages them and revokes them
   when the account password changes. If Google withdraws them, reading
   Gmail needs Google's sign-in, with its verification. Check: set one up
   on the owner's Gmail, and watch Google's announcements.
5. **Building Memento beats using what exists.** pckt already reads Indian
   bank SMS and email on the phone, merges duplicates and keeps budgets. If
   it serves the owner, contributing to it may cost less than building
   Memento. Check: use pckt for a week with the owner's own banks, and note
   what is missing.
6. **Others have the problem too.** The evidence is the owner's own months.
   Check: ask five friends who use UPI and cards how they found out where
   last month's money went, and what they did the last time they split a
   bill: about what happened, not about the app.
7. **A prompt within seconds works on Android.** An SMS that arrives while
   the app is closed has to start the app's core in the background
   ([ADR 1](../adr/0001-flutter-with-a-pure-dart-core.md)). Check: a
   prototype on the owner's phone that notifies on a bank SMS with the app
   closed.
