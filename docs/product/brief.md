# Memento

Memento is an open source, privacy-first personal finance app for Android,
for people in India whose money moves through several bank accounts, cards
and UPI. It records each payment in and out from the bank's SMS and email
alerts as it arrives, asks what the payment was for while the user still
remembers, splits shared expenses with friends, and shows spending against a
plan of where the money should go. Everything stays on the phone. The Indian
apps that capture payments automatically send the data to their own servers
and are paid for by loans, cards, investing or subscriptions; the private
budgeting apps make the user type each payment in; and the few open source
apps that read Indian bank alerts on the phone are weeks old, and none of
them describes a prompt at the moment of spending or splitting a bill with
friends. Its first user is its owner, who builds it for their own money.

## Problem

Money moves through many channels: several bank accounts, credit and debit
cards, UPI. Nothing shows in one place what came in and what went out. In
October 2026, India made about 25.47 billion UPI payments, and about 12.7
crore credit cards and 104 crore debit cards were outstanding
([survey](../research/existing-products.md#how-fragmented-an-indian-users-money-is)).

The owner's own month shows what this costs. The salary is credited on one
day. Over the days that follow, credit card bills, EMIs and everyday
payments go out through different channels, and about two weeks later the
money is gone and the owner can't say what it went on. The only way to find
out is to go through bank and card statements months later, when most of
the payments can no longer be remembered. Without knowing where the money
went, there is nothing to plan the next month's spending from.

Not every movement is spending or income. A friend paying back, a refund, a
transfer between the owner's own accounts or a credit card bill payment is
neither, and counting it as one gives the wrong picture.

Shared expenses are one part of this. When the owner goes out with friends
and pays, the expense isn't entered in a splitting app that day. It is
sorted out months later, when nobody remembers the details.

Today the owner manages by reading statements long after the month, and by
entering shared expenses in Splitwise late.

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
- **People outside India.** The alerts it reads, and the rules it works
  within, are Indian banks'.
- **Businesses, bookkeeping, and tracking investments or net worth.**
- **Anyone who wants their bank linked to the app, or the app to make
  payments.**

## What exists already

The [survey](../research/existing-products.md) read more than 20 products
and projects on 2026-11-25. None meets the need in full.

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
  banks and imports statements, with a build that has no internet access.
  Both appeared in October 2026 under GPL-3.0, are installed from GitHub
  rather than Google Play, and neither describes a prompt at the moment of
  spending or splitting a bill with friends.

No product read describes a prompt at the moment of spending. Of those
read, the only one that both captures automatically and splits bills with
friends is FinArt, which is closed, paid, and declares that it collects
SMS.

## Goals

- **Nothing to type.** Money in and out is recorded from bank SMS and email
  alerts as they arrive, and a statement fills in what had no alert.
- **Asked while they remember.** Within seconds of an SMS alert, a
  notification asks what the payment was for, with one tap to add a note, a
  category or a split. Email alerts are fetched from time to time rather
  than pushed, so their prompt comes later.
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

Each rule links the research note that quotes it, with the date it was
read. What a source leaves unsettled is marked **Open**: the owner's
question, which they may put to a lawyer. Nothing here says that Memento
complies with a rule.

### Google Play: SMS capture

Only the default SMS app may read SMS, unless Google grants a temporary
exception. The one that fits Memento is "SMS-based money management", "For
example, apps that track and manage budget", which covers READ_SMS and
RECEIVE_SMS and is "Subject to Google Play review and approval". It is asked
for with a Permissions Declaration Form and a demo video, and its review
"may require up to several weeks". SMS capture must be the app's core
feature, promoted in its store description, and the app may not share a
user's non-financial SMS
([store rules](../research/store-and-platform-rules.md#1-google-play-sms-permission-groups)).

**Open:** whether Google grants it to Memento. Only a submission settles it:
the first risk below.

### Google Play: privacy policy and declarations

Every app links a privacy policy in Play Console and inside the app, on a
public web page, even one that collects no data. Data processed only on the
phone need not be declared as collected on the Data safety form, but the
form is still completed. Where the app reads personal data in a way the
user may not expect, such as in the background, its permission request is
preceded by a prominent disclosure in the app
([store rules](../research/store-and-platform-rules.md#2-google-play-data-safety-section-and-privacy-policy)).
Every app also completes the Financial features declaration, whose list has
no entry for expense tracking
([store rules](../research/store-and-platform-rules.md#3-google-play-financial-features-declaration)).

**Open:** whether Memento declares "Other" or that it provides no financial
features.

### Google Play and Android: publishing as an individual

A personal developer account created after 13 November 2023 runs a closed
test with at least 12 testers for 14 days before it can publish. An
organization account, which needs a D-U-N-S number, is required for
"Financial products and services, including banking, loans, stock trading,
investment funds, cryptocurrency software wallets, and cryptocurrency
exchanges"
([store rules](../research/store-and-platform-rules.md#4-google-play-publishing-as-an-individual)).
An app installed from outside Google Play will need a verified developer
once Android's developer verification reaches India, due "globally ... in
2027"; apps on Google Play are registered automatically
([store rules](../research/store-and-platform-rules.md#5-android-developer-verification)).

**Open:** whether Google counts a tracker that moves no money as a financial
product or service: the second risk below.

### Email providers: email capture

- **Gmail over IMAP** with an app password needs 2-Step Verification, and
  isn't available to work or school accounts, to security-key-only 2-Step
  Verification or to Advanced Protection. Google revokes app passwords when
  the account password changes and says they "aren't recommended"; its
  pages announce no removal
  ([store rules](../research/store-and-platform-rules.md#7-google-app-passwords-email-capture-first-route)).
- **Gmail through Google's API** with `gmail.readonly` is a restricted
  scope: a public release needs Google's verification, while the
  developer's own use, or fewer than 100 users, does not
  ([store rules](../research/store-and-platform-rules.md#8-gmail-api-restricted-scopes-possible-later-route)).
  **Open:** whether an app with no server also needs the yearly security
  assessment; Google's pages disagree.
- **Outlook.com** requires OAuth2 for IMAP; password sign-in ended on
  16 September 2024
  ([store rules](../research/store-and-platform-rules.md#9-outlookcom-imap-with-a-password)).

### Apple: the iPhone version

Every app links a privacy policy in App Store Connect and inside the app
(guideline 5.1.1(i)). Apps "in highly regulated fields (such as banking and
financial services ...) or that require sensitive user information should
be submitted by a legal entity that provides the services, and not by an
individual developer" (5.1.1(ix))
([store rules](../research/store-and-platform-rules.md#6-apple-app-review-guidelines-ios-later)).

**Open:** whether 5.1.1(ix) covers Memento.

### Indian law: personal data

India's Digital Personal Data Protection Act, 2023 does "not apply to ...
personal data processed by an individual for any personal or domestic
purpose". On its face that covers the user recording their own payments,
and the names of the friends they split with
([Indian law](../research/indian-law.md#1-digital-personal-data-protection-act-2023-definitions-and-section-3)).
In the local-only build the developer receives no data.

**Open:** whether writing the app a user runs makes the developer a "Data
Fiduciary"; the Act doesn't say. The cloud build would hold friends' split
records on a server the developer runs, and how the Act applies to that is
a question for the change that adds it. The duties of the DPDP Rules, 2025
on notice, safeguards, breaches, retention and people's rights come into
force about May 2027
([Indian law](../research/indian-law.md#2-digital-personal-data-protection-rules-2025-notification-and-commencement)).

### Indian sector rules: what alerts exist

- **No bank data route for an individual.** An Account Aggregator's data
  user must be "registered with and regulated by any financial sector
  regulator"
  ([Indian law](../research/indian-law.md#3-rbi-account-aggregator-framework)).
- **SMS alerts shrink from 2027.** Until 31 December 2026, commercial banks
  must send an SMS for every electronic banking transaction. From
  1 January 2027 they must send one only "for all EBTs of value more than
  ₹500"; at or below that, each bank decides. They must send "email alerts
  for all EBTs, wherever email address is provided by the customer"
  ([Indian law](../research/indian-law.md#4-rbi-banks-sms-alerts-for-electronic-transactions)).
  Email is the source the rules keep complete.
- **SMS sender headers.** Commercial SMS come only from headers registered
  with the telecom operators, suffixed "-T" for transactional, "-S" for
  service, "-P" for promotional and "-G" for government messages. The
  suffix helps tell an alert from a promotion; it doesn't prove which bank
  sent it
  ([Indian law](../research/indian-law.md#5-trai-commercial-sms-headers-dlt-and-suffixes)).

### Licences

Memento is licensed AGPL-3.0-or-later: whoever distributes it offers its
source under the same licence. The licences it may take in, proposed for
the owner's decision ([licences](../research/licences.md)):
- **Taken in:** MIT, BSD-2-Clause, BSD-3-Clause, Apache-2.0, ISC, Zlib,
  MPL-2.0 unless marked "Incompatible With Secondary Licenses", and public
  domain dedications: SQLite's (`blessing`), Unlicense and CC0-1.0. The FSF
  lists each as compatible with the GNU GPL.
- **Not taken in from others:** GPL, LGPL and AGPL code. The FSF reads
  Apple's App Store terms as incompatible with every version of the GPL and
  AGPL, and a post on its blog says the same of the LGPL, so code from
  others under them would tie an iPhone release to its authors'
  permission. The owner's own code is theirs to license.

What Memento builds on fits: Flutter is BSD-3-Clause, drift is MIT, and
SQLite is in the public domain
([licences](../research/licences.md#2-licences-of-flutter-drift-and-sqlite)).

**Open:** whether MPL-2.0 code can ship through the App Store; Apple's
current terms were not read.

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
   can't read SMS, and capture rests on email, statements and typing. axio
   describes itself on Google Play as "an SMS-based money management app",
   so the category exists there; whether Memento is granted it, only its
   declaration settles. Check: submit the Permissions Declaration Form with
   the first closed-test build, weeks before a public release.
2. **An individual may publish it.** If Google counts a tracker as a
   "financial product or service", Google Play needs an organization
   account with a D-U-N-S number, and Apple's 5.1.1(ix) asks the same of
   the iPhone version. Check: ask Play Console support before registering
   the developer account.
3. **Alerts are enough to reach 90%.** From 1 January 2027, banks may stop
   SMS for payments of ₹500 or less, and HDFC Bank already stopped SMS for
   small UPI payments in 2024, by a press report. Email alerts stay
   required wherever the customer gave an email address, so a bank that
   stops small SMS leaves the first success criterion resting on email
   capture. Check: count one month of the owner's payments against the SMS
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
