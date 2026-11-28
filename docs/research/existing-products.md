# What exists already: money trackers for India

The products and projects that address the problem Memento solves. Every
fact below was read on 2026-11-25 from the source cited in brackets; the
sources list gives the URLs.
Play Store pages were read for India (`hl=en_IN&gl=IN`). "Play data safety"
is the developer's own declaration on Google Play, where "collected" means
"transmitting data from your app off a user's device" [S48].

Each product is judged against eight needs: 1 automatic capture from SMS and
email; 2 a prompt within seconds of a spend; 3 one transaction from several
sources recorded once; 4 own transfers, card bills, refunds and friends'
paybacks kept out of spend and income; 5 splitting with friends, balances,
partial settling; 6 budgets; 7 data stays on the phone, no company server,
no bank login or Account Aggregator (AA) consent; 8 open source.

## Summary: what no product does

- **No product meets all eight needs.** None of the sources read describes
  need 2, a prompt at the moment of spending to add a note or split it, for
  any product. Need 4 beyond own-account transfers (card bills, refunds,
  friends paying back) is described by none either.
- **The commercial Indian trackers trade privacy for revenue.** axio, Money
  View, ET Money, INDmoney and CRED all declare on Play that they collect SMS,
  that is, SMS data leaves the phone, and they earn from loans, credit cards
  or investments.
  The AA apps (Fold, Jupiter, INDmoney, CRED) need AA consent and hold the
  data on their servers by design.
- **The private, closed-source options stop short.** FinArt reads SMS, email
  and notifications and splits group bills, but is closed and paid, and its
  Play declaration says SMS are collected for analytics despite its "Private
  Mode". Bluecoins reads SMS and bank-app notifications on the phone, but has
  no email capture and no splitting with friends.
- **The splitting apps don't track your own money.** Splitwise, Splid and
  Tricount do balances and settling up well, but every entry is typed in, and
  they keep no budgets or personal ledger.
- **The open source finance apps miss India's capture problem.** Cashew,
  Actual and Firefly III are mature, but none reads Indian bank SMS or email
  as its core path; Actual and Firefly have no bank sync for India.
- **The closest match is a handful of new open source Android apps** from
  Oct 2026: pckt (SMS + email, dedup, transfers, on-device, GPL-3.0) and Kosh
  (SMS, India-specific, offline build, IOUs, GPL-3.0). Both are weeks old,
  with one and two contributors on GitHub, are sideloaded rather than on
  Play, and neither describes group splitting with settle-up or a
  spend-time prompt.
- Google Play permits non-default apps to read SMS for "SMS-based money
  management … apps that track and manage budget", with the limit that such
  apps "may not exfiltrate or share non-financial or personal SMS history"
  [S47]; several small on-device SMS trackers are listed on Play [S45].

## How fragmented an Indian user's money is

- UPI: 2,54,666.92 lakh transactions (about 25.47 billion) worth
  ₹31,52,929 crore (about ₹31.53 lakh crore) in October 2026, up from
  2,07,009.21 lakh in October 2025 [S49, RBI Payment System Indicators,
  October 2026, provisional]. Inc42, citing NPCI, reports the same 25.47
  billion and ₹31.53 lakh crore, up 5.8% in volume from September's 24.07
  billion [S50]. NPCI's own statistics page refused the request (HTTP 403).
- Cards outstanding at end October 2026: 1,267.16 lakh credit cards (about
  12.7 crore) and 10,410.07 lakh debit cards (about 104 crore) [S49].
- CRED's claim at its 2024 launch of CRED Money: "nearly 70% of India's
  affluent population struggles with having their finances fragmented across
  multiple platforms", and its average customer makes about 200 transactions
  a month [S20; a company claim reported by TechCrunch].

## Table

Needs missed: a number means the product's own pages show it lacks that
need, or it is absent from a feature list that would name it; "?" means the
sources read don't say; "~" means partly met.

| Product | Capture | Where data goes | Paid for by | Status (2026-11-25) | Needs missed |
|---|---|---|---|---|---|
| axio (ex-Walnut) | Bank SMS | Company servers: Play declares SMS, name, phone, credit score collected | Loans, Pay Later, fixed deposits | Active; Amazon-owned since Sep 2025 | 1~ (no email), 5, 7, 8; ? 2, 3, 4 |
| FinArt | SMS, email, app notifications | "Private Mode" on device; Play declares SMS and financial info collected for analytics | Subscription after 5-day trial | Active | 7~, 8; ? 2, 3, 4, 5~ |
| Money View (Money Manager) | Bank SMS | Play declares SMS collected | Personal loans | App active as a loan/UPI app; tracker's presence unclear | 5, 7, 8; ? 2, 3, 4, 6 |
| ET Money | None named in its listing | Play declares SMS collected | Investments, loans | Pivoted to wealth; listing no longer names expense tracking | Not a tracker per its listing |
| INDmoney | Linked bank accounts (method not stated) | Play declares email and SMS collected | Broking, US stocks, margin funding | Active | 1, 5, 6?, 7, 8; ? 2, 3, 4 |
| Fold | AA; Gmail for card emails on Plus | AA, then Fold's servers | Fold Plus ₹349/month, ₹799/quarter, ₹999/year | Active | 1~, 5~, 6?, 7, 8; ? 2, 3, 4 |
| Jupiter | AA (e.g. Finvu) | AA, then Jupiter's servers | Co-branded credit card, salary accounts, loans | Active | 1, 5, 7, 8; ? 2, 3, 4 |
| CRED (CRED Money) | AA (2024 launch); Play declares SMS and email collected | CRED's servers | Payments, rewards, lending; CRED Money not monetised | Active | 1~, 5, 6?, 7, 8; ? 2, 3, 4 |
| Money Manager (Realbyte) | Typed in | On device; Excel backup | Ads; paid version | Active | 1, 2, 3, 5, 8 |
| Wallet (BudgetBakers) | Bank sync, typed in | BudgetBakers cloud | Premium (₹199 to ₹4,999 on India App Store) | Active | 1, 5, 7, 8; ? 2, 3, 4 |
| YNAB | Bank import (US, CA, UK, EU), typed in | YNAB cloud | $14.99/month or $109/year | Active | 1, 2, 5, 7, 8; ? 3, 4 |
| Goodbudget | Typed in; bank sync US only | Goodbudget cloud | Premium $10/month or $80/year | Active | 1, 2, 3, 5, 7, 8 |
| Bluecoins | Bank SMS and bank-app notifications (Android) | On device; backup to user's own Drive, Dropbox, OneDrive | Ads; one-time Premium | Active | 1~ (no email), 5, 8; ? 2, 3, 4 |
| Splitwise | Typed in | Splitwise servers | Ads and a daily expense cap; Pro subscription | Active | 1, 2, 3, 4, 6~, 7, 8 |
| Splid | Typed in | On device; optional sync | Free; Excel export purchase | Active (Play update Aug 2025) | 1, 2, 3, 4, 6, 7~, 8 |
| Tricount (bunq) | Typed in; bunq card auto-add | Tricount servers | Free; owned by bunq, which it links to | Active | 1, 2, 3, 4, 6, 7, 8 |
| Cashew | Typed in; notification/SMS automation | On device; optional own Google Drive | Cashew Pro (one-time or subscription) | Play active; GitHub quiet since Mar 2026 | 1~, 3, 5~; ? 2, 4 |
| Actual Budget | Typed in, file import, bank sync (no India) | Local; optional self-hosted sync, optional E2E encryption | Free; donations; paid hosting by others | Active | 1, 2, 5; ? 3, 4; no Android app among its install options |
| Firefly III | Typed in, CSV/CAMT, third-party bank providers | User's own server | Free; hosting referrals | Active | 1, 2, 5, 7~; ? 3, 4 |
| pckt | Bank SMS and email (IMAP) | On device, encrypted | Free | New (Oct 2026), sideloaded APK | 4~, 5; ? 2 |
| Kosh | Bank SMS (India), CSV statements | On device; offline build has no internet | Free | New (Oct 2026), sideloaded APK | 1~, 2, 3~, 4~, 5~ |
| XPENC | Shared-in SMS or screenshot, typed in | On device | Free | Active (Nov 2026); Play and F-Droid | 1; ? 2, 3 |
| kharcha | Allowlisted bank SMS | On device; optional encrypted backup to user's own server | Free | One release (Oct 2026), no commits since | 1~, 5; ? 2, 3, 4 |

## Product notes

### India, automatic from SMS

**axio (formerly Walnut).** Play: "an SMS-based money management app" with
budgets, bill reminders, card dues, notes, tags and receipt photos; "axio
(formerly known as Capital Float, Walnut & Walnut 369)"; Pay Later, personal
loans at 14% to 35% a year, fixed deposits; SMS permission also used for
loan fraud checks and FD device binding; updated 15 Jul 2026; 1Cr+ downloads
[S1]. The listing says it "does not read your personal SMS or upload any
sensitive data", but its Play data safety declares SMS, name, phone number,
address, user IDs and credit score collected, and location and name shared
[S1]. Its privacy policy page does not mention SMS [S3]. Amazon completed its
acquisition of Axio on 4 Sep 2025 [S2]. Does well: the longest-running
automatic SMS tracker in India, with bills and card dues.

**FinArt.** Play: reads "transaction SMS, emails and app notifications"; UPI,
card and bank tracking; bill and subscription tracking; budgets; "Split group
expenses, shared bills and EMIs"; family sync; ad-free; 5-day trial, then
subscription; "Private Mode — SMS text or transaction data never leaves your
device"; backup to the user's own Google Drive; updated 28 Oct 2026; 10L+
downloads [S4]. Its Play data safety declares SMS (optional) and financial
info collected for analytics, and "Data can't be deleted" [S4]. iPhone
version: Premium $2.99/month or $24.99/year in the US store; "Data linked to
you" includes financial info and emails or text messages [S5]. Company:
Frienteer Software Private Limited [S6]. INR price not published on its site
[S6]. Does well: the widest capture of any commercial app, plus splits.

**Money View Money Manager.** Money View's FAQ describes SMS-based tracking,
"we only get partial account numbers as sent by banks via SMS", and Backup &
Restore [S8]. The current Moneyview Play listing (updated 18 Nov 2026) sells
personal loans (APR 17% to 45%), home loans, UPI and gold, and does not
mention a money manager; it declares SMS collected [S7].

**ET Money.** The Play listing (package `com.smartspends`, updated 23 Nov
2026, 1Cr+) now describes mutual funds, SIFs, FDs, bonds, NPS, US stocks and
loans, and no expense tracking; it declares SMS collected (optional) [S9].

**Others on Play.** Small Indian SMS trackers that claim on-device data:
PaisaSync ("your transactions stay on your device"; 1K+ downloads; declares
no data collected), Vrid (10K+), TrakFi (50+), AuraSpend (10+) [S45].
"Bachat" turned up Bachatt, a savings and investment app, not a tracker:
dropped [S46].

### India, via Account Aggregator or bank links

**INDmoney.** A broking and investing app (Indian and US stocks, F&O, IPOs,
margin funding up to 75%); "Track Your Net Worth … Unified view of all assets,
investments & expenses … Link bank accounts, credit cards" [S10]. Its bank
tracker shows combined balances, categories and "Spending Drift", but does
not say how accounts are linked [S11]. Play data safety declares emails and
SMS collected [S10].

**Fold.** "Fold establishes connection to your Banks through the Government
regulated Account Aggregator Framework"; "No Email scraping", "No SMS
scraping"; iOS, Android and web; "Backed by Zerodha" [S12]. App Store India:
Plus subscribers can connect Gmail to sync credit cards from email; "Spaces"
for family or shared expenses; Plus ₹349/month, ₹799/quarter, ₹999/year,
"Believer" ₹24,999; budgets not mentioned [S13]. Play: 1L+, updated 25 Nov
2026 [S14]. Does well: clean, ad-free AA tracking with net worth.

**Jupiter.** Data "with your consent via licensed Account Aggregators like
Finvu"; auto-categorised spends; monthly budget alerts [S16]. Play: a
co-branded CSB Bank RuPay credit card, salary accounts, mini loans, UPI; "Send/
read SMS: Register UPI and track financial transactions and bills"; 1Cr+,
updated 19 Nov 2026 [S15].

**CRED.** CRED Money launched July 2024 on the AA framework: balances and
transactions across banks, recurring payments, search by merchant; "won't be
monetizing the new feature" [S20, news]. Play today: card bill payments, UPI,
"Track your credit score & bank balance", "Spot hidden charges & duplicate
spends"; 5Cr+, updated 13 Nov 2026; declares emails and SMS collected [S19].

**Fi: dropped.** Fi wound down banking on its app in March 2026; accounts
moved to Federal Bank's FedMobile; the company is refocusing on AI and
enterprise systems [S17, news]. Its Play listing (`com.epifi.paisa`) returns
404 [S18].

### Manual or bank-sync budgeting

**Money Manager (Realbyte).** Typed entry with double-entry bookkeeping,
budgets, card settlement dates, transfers between assets, recurring entries,
Excel backup; paid version removes ads, lifts the 15-asset limit and adds PC
editing over Wi-Fi; 1Cr+, updated 25 Nov 2026 [S21]. Its data safety lists
SMS (optional) among data collected, but the listing describes no SMS feature
[S21].

**Wallet by BudgetBakers.** "tracking expenses automatically with bank
synchronization"; "Your financial data is securely synced to the cloud";
shared accounts [S22]. App Store India: "4,000 participating banks
worldwide"; Premium purchases from ₹199 to ₹4,999 (plan mapping not shown)
[S23].

**YNAB.** Zero-based budgeting, plans shared with up to six people; 34-day
trial [S24]; $14.99/month or $109/year; "Direct import currently supports
select US, Canadian, UK, and EU Banks" [S25]. Play rating 3.47 [S24].

**Goodbudget.** Envelope budgeting synced across devices and web [S26]. Free:
10 regular and 10 annual envelopes, one account, two devices, one year of
history; Premium $10/month or $80/year [S27]. Bank sync is Premium, through
Plaid, "in the United States only" [S28].

**Bluecoins.** "Watches push notifications from banking apps and SMS and
creates the transactions for you — no bank login, ever"; "Your data lives on
your device, backs up to your own Google Drive, Dropbox, or OneDrive"; free
with ads, Premium "Pay once — not a subscription" [S30]. The push-notification
switch "is a premium feature"; SMS has its own switch; entries are created
automatically, with no confirmation step described [S31]. Play: declares no
data collected; 10L+, updated 9 Nov 2026 [S29]. Does well: the most private
closed-source auto-capture, with strong budgets and reports.

### Splitting

**Splitwise.** Groups, IOUs, settle up "by recording cash payments or using
our integrations", offline entry; 1Cr+, updated 25 Nov 2026; declares no data
shared [S32]. Pro adds "Unlimited expenses", no ads, receipt scanning, search,
charts, and bank card import (US only) [S33], which implies a capped,
ad-supported free tier; the cap's size was not verified. India App Store: ten
Pro purchases from ₹49 to ₹1,399, plan mapping not shown [S34].

**Splid.** "Splid is free!"; no sign-up; offline groups, optional sync to
enter expenses together; 150+ currencies [S35]. Excel export is an in-app
purchase; Play updated 23 Aug 2025; 10L+ [S35].

**Tricount.** Owned by bunq (Play developer); "100% free with no ads or
limits"; offline use; a bunq Card adds shared expenses automatically; 1Cr+,
updated 19 Nov 2026 [S36]. Data safety declares device IDs shared for
advertising or marketing [S36].

### Open source

**Cashew (GPL-3.0).** Budgets by any period, goals, subscriptions, borrowed
and lent; data stored locally, with Google Drive for backup and sync;
"Cashew does not collect/store any of your financial data on a central
server" [S37]. Its FAQ lists "Add a transaction from another app's
notification / SMS message" under Automation; it "doesn't natively support
splitting transactions" [S37]. Play: 5L+, updated 16 Oct 2026; declares no
data collected [S37]. GitHub: last commit 9 Mar 2026, last GitHub release
5.3.4 on 1 Jul 2024, about 4.8k stars [S37]. Does well: the most polished
private budgeting app.

**Actual Budget (MIT).** "a local-first personal finance tool … 100% free
and open-source"; envelope budgeting; desktop apps, Docker or managed
hosting [S38]. Optional self-hosted sync and end-to-end encryption [S38].
Bank sync providers cover New Zealand, Europe, North America and Brazil;
India is not listed [S38]. Release v26.11.0 on 2 Nov 2026 [S38].

**Firefly III (AGPL-3.0).** Self-hosted, double-entry, budgets, rules; "will
never contact external servers until you explicitly tell it to"; imports via
CSV, CAMT and third-party data providers [S39]. Release v6.7.9 on 11 Oct 2026
[S39].

**pckt (GPL-3.0).** Reads bank, card and UPI alerts by SMS and by email (IMAP
app passwords; optional Gmail OAuth in self-built versions); "A scoring dedup
engine (same reference, account, time, merchant, channel) merges them";
"Transfers between your own accounts are recognised and kept out of spend";
budgets, recurring detection; SQLCipher database on the phone; optional LLM
with the user's own key or on-device; "Built for India first"; Android 11+,
APK from GitHub [S40]. Created 19 Oct 2026, release v1.0.1 on 21 Oct 2026,
12 stars [S40]. The nearest match to needs 1, 3, 4, 6, 7 and 8.

**Kosh (GPL-3.0).** "built for Indian banking": detailed SMS parsing for six
banks, sender recognition for nine more; card bills from SMS with "mark paid"
recording the transfer; CSV statement import "skipping rows already imported
from SMS"; splits across categories and money lent or borrowed; budgets with
an envelope mode; an "Offline edition" with "no INTERNET permission at all";
household sync over Wi-Fi; "optional daily digest notification"; "Kosh isn't
on the Play Store" [S41]. Created 14 Oct 2026, v2.6.1 on 22 Oct 2026, 21
stars [S41].

**XPENC (MIT).** Offline-first; transfers, budgets, envelope mode; "Persons —
dues/loans with running balances, group splits, UPI Pay/Request"; bank SMS or
a screenshot shared into the app, "no `READ_SMS`, no network"; on Play and
F-Droid [S42]. The closest open source app on splitting.

**kharcha (MIT).** An Expo app that reads SMS from enabled bank sender IDs;
optional encrypted backup to a server the user deploys; budgets [S43].
v1.0.0 on 4 Oct 2026, last commit 5 Oct 2026 [S43].

**Library:** transaction-sms-parser (TypeScript, MIT, 62 stars, last commit
27 May 2026) parses bank, card and wallet SMS [S44].

## Sources

All read 2026-11-25. Play listings were read with `hl=en_IN&gl=IN`; each data
safety page is `https://play.google.com/store/apps/datasafety?id=<package>`.
GitHub facts (licence, dates, stars, releases) come from the GitHub API.
"News" marks reputable press; "secondary" marks anything else.

- S1 axio, Play: https://play.google.com/store/apps/details?id=com.daamitt.walnut.app (and its data safety page)
- S2 Amazon, "Amazon acquires Axio" (4 Sep 2025): https://www.aboutamazon.in/news/company-news/amazon-acquires-axio
- S3 axio privacy policy: https://axio.co.in/privacy-policy/
- S4 FinArt, Play: https://play.google.com/store/apps/details?id=com.finart (and data safety)
- S5 FinArt, App Store US: https://apps.apple.com/us/app/finart-sms-expense-tracker/id6748001842
- S6 FinArt site: https://finart.app
- S7 Moneyview, Play: https://play.google.com/store/apps/details?id=com.whizdm.moneyview.loans (and data safety)
- S8 Money View FAQ: https://moneyview.in/money-view-app-faq
- S9 ET Money, Play: https://play.google.com/store/apps/details?id=com.smartspends (and data safety)
- S10 INDmoney, Play: https://play.google.com/store/apps/details?id=in.indwealth (and data safety)
- S11 INDmoney bank tracker: https://www.indmoney.com/features/track-bank-account
- S12 Fold site: https://fold.money
- S13 Fold, App Store India: https://apps.apple.com/in/app/fold-money/id1626994334
- S14 Fold, Play: https://play.google.com/store/apps/details?id=money.fold.marble (and data safety)
- S15 Jupiter, Play: https://play.google.com/store/apps/details?id=money.jupiter (and data safety)
- S16 Jupiter Money: https://jupiter.money/money
- S17 TechCrunch, "India neobank Fi winds down banking services on its platform" (11 Mar 2026; news): https://techcrunch.com/2026/03/11/india-neobank-fi-winds-down-banking-services-on-its-platform
- S18 Fi, Play (404): https://play.google.com/store/apps/details?id=com.epifi.paisa
- S19 CRED, Play: https://play.google.com/store/apps/details?id=com.dreamplug.androidapp (and data safety)
- S20 TechCrunch, "CRED launches personal finance manager for India's affluent" (24 Jul 2024; news): https://techcrunch.com/2024/07/24/cred-launches-personal-finance-manager-for-indias-affluent/
- S21 Money Manager (Realbyte), Play: https://play.google.com/store/apps/details?id=com.realbyteapps.moneymanagerfree (and data safety)
- S22 Wallet, Play: https://play.google.com/store/apps/details?id=com.droid4you.application.wallet (and data safety)
- S23 Wallet, App Store India: https://apps.apple.com/in/app/id1032467659
- S24 YNAB, Play: https://play.google.com/store/apps/details?id=com.youneedabudget.evergreen.app
- S25 YNAB pricing: https://www.ynab.com/pricing
- S26 Goodbudget, Play: https://play.google.com/store/apps/details?id=com.dayspringtech.envelopes
- S27 Goodbudget, subscribe: https://goodbudget.com/help/billing/subscribe-to-goodbudget/
- S28 Goodbudget, bank sync: https://goodbudget.com/help/automatic-bank-sync/which-banks-can-i-link-to-my-accounts/
- S29 Bluecoins, Play: https://play.google.com/store/apps/details?id=com.rammigsoftware.bluecoins (and data safety)
- S30 Bluecoins site: https://www.bluecoinsapp.com/
- S31 Bluecoins guides: https://ram.bluecoinsapp.com/guide/bank-notifications/ and https://www.bluecoinsapp.com/sms/
- S32 Splitwise, Play: https://play.google.com/store/apps/details?id=com.Splitwise.SplitwiseMobile (and data safety)
- S33 Splitwise Pro: https://www.splitwise.com/pro
- S34 Splitwise, App Store India: https://apps.apple.com/in/app/splitwise/id458023433
- S35 Splid: https://splid.app/english and https://play.google.com/store/apps/details?id=splid.teamturtle.com.splid
- S36 Tricount: https://tricount.com/en and https://play.google.com/store/apps/details?id=com.tribab.tricount.android (and data safety)
- S37 Cashew: https://play.google.com/store/apps/details?id=com.budget.tracker_app, https://github.com/jameskokoska/Cashew, https://cashewapp.web.app/faq.html
- S38 Actual: https://actualbudget.org/, https://actualbudget.org/docs/advanced/bank-sync, https://github.com/actualbudget/actual
- S39 Firefly III: https://github.com/firefly-iii/firefly-iii, https://github.com/firefly-iii/data-importer
- S40 pckt: https://github.com/pritam-ravani/pckt
- S41 Kosh: https://github.com/AIM-IT4/kosh
- S42 XPENC: https://github.com/PATILYASHH/XPENC and https://play.google.com/store/apps/details?id=com.yash.xpenc
- S43 kharcha: https://github.com/cneuralnetwork/kharcha
- S44 transaction-sms-parser: https://github.com/saurabhgupta050890/transaction-sms-parser
- S45 Play listings: https://play.google.com/store/apps/details?id=com.paisasync.app, ...?id=in.vrid, ...?id=in.trakfi.ledger, ...?id=com.awbuilds.auraspend
- S46 Bachatt, Play: https://play.google.com/store/apps/details?id=app.bachatt.customer
- S47 Google Play, SMS and Call Log permissions: https://support.google.com/googleplay/android-developer/answer/10208820
- S48 Google Play, data safety definitions: https://support.google.com/googleplay/android-developer/answer/10787469
- S49 RBI, Payment System Indicators, October 2026: https://rbi.org.in/Scripts/PSIUserView.aspx?Id=65
- S50 Inc42, "UPI Transactions Rise 5.8% MoM To Record 25.47 Bn In October" (2 Nov 2026; news): https://inc42.com/buzz/upi-transactions-rise-5-8-mom-to-record-25-47-bn-in-october/
- Not read (HTTP 403): NPCI UPI statistics, https://www.npci.org.in/what-we-do/upi/product-statistics

## Not verified

- **Need 2 (a prompt within seconds) for every product**: no source read
  describes one; the products' apps were not installed or tried.
- **Need 3 and need 4** for every product except pckt (dedup, own transfers),
  Kosh (SMS against CSV, card bill "mark paid") and XPENC (transfers, dues).
- NPCI's own UPI page (HTTP 403); the UPI figures rest on RBI [S49] and Inc42
  [S50].
- Splitwise's free daily expense cap (number) and which ₹ price is which Pro
  plan; third-party pages that state them refused the request.
- Prices: FinArt in ₹, Bluecoins Premium, Cashew Pro, Realbyte's paid
  version, Wallet's plan mapping.
- Whether Money View still ships its Money Manager, and whether ET Money
  still tracks expenses (etmoney.com could not be fetched); how INDmoney
  links accounts; CRED Money today beyond its 2024 launch; whether Fold has
  budgets; whether axio uses SMS for credit decisions (its policy is silent).
- Wallet's bank coverage in India; whether Realbyte reads SMS (its data
  safety lists SMS, its listing doesn't); how Cashew's notification/SMS
  automation parses and whether it needs Pro; what FinArt's Private Mode
  covers; where Splid and Tricount store synced groups; whether Fi's app
  still runs for existing users; the small Play trackers [S45] beyond their
  listings. iPhone apps were not surveyed beyond the App Store pages cited.
