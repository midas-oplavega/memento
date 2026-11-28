# Indian law and sector rules

The Indian laws and regulators' rules that bear on Memento: data protection, the
Account Aggregator framework, banks' transaction alerts and SMS sender headers.
All sources were read on 2026-11-25. Each section quotes the words its finding
rests on, says what it may mean for Memento, and names what the source leaves
open. Sources are official unless marked secondary. This is not legal advice,
and it does not say that Memento complies with any rule.

## 1. Digital Personal Data Protection Act, 2023: definitions and section 3

**Source:** The Digital Personal Data Protection Act, 2023 (No. 22 of 2023), Gazette of India Extraordinary,
Part II, Section 1, 11 August 2023. MeitY copy:
https://www.meity.gov.in/static/uploads/2024/06/2bf1f0e9f04e6fb4f8fef35e82c42aa5.pdf. Official. The India
Code copy (https://www.indiacode.nic.in/bitstream/123456789/22037/2/a2023-22.pdf) returned 403, then 504.

**Quoted words:**
- s.2(i): "“Data Fiduciary” means any person who alone or in conjunction with other persons determines the
  purpose and means of processing of personal data;"
- s.2(j): "“Data Principal” means the individual to whom the personal data relates"
- s.2(s): "“person” includes— (i) an individual;"
- s.2(t): "“personal data” means any data about an individual who is identifiable by or in relation to such
  data;"
- s.2(x): "“processing” in relation to personal data, means a wholly or partly automated operation or set of
  operations performed on digital personal data, and includes operations such as collection, recording,
  organisation, structuring, storage, adaptation, retrieval, use, alignment or combination, indexing,
  sharing, disclosure by transmission, dissemination or otherwise making available, restriction, erasure or
  destruction;"
- s.3: "Subject to the provisions of this Act, it shall— (a) apply to the processing of digital personal data
  within the territory of India where the personal data is collected–– (i) in digital form; ... (c) not
  apply to— (i) personal data processed by an individual for any personal or domestic purpose; and (ii)
  personal data that is made or caused to be made publicly available by— (A) the Data Principal to whom such
  personal data relates; or (B) any other person who is under an obligation under any law ..."

**What it means for Memento:**
- (a) *User on their own data.* Reading, parsing and storing alerts is "processing". A user doing this for
  their own money is "an individual" processing "for any personal or domestic purpose", and s.3(c)(i) says
  the Act does "not apply" to that. This governs capture, parsing and on-device storage.
- (b) *Developer who never receives data.* The developer performs no "operation ... on digital personal
  data". Whether writing the software a user runs alone counts as determining "the purpose and means of
  processing" (s.2(i)) is not settled by the text. Any feature that sends data to the developer (crash
  reports, sync, hosted backup) would make the developer a processor of it, and the question changes.
- (c) *Friends' names.* A friend's name with what they owe is "data about an individual who is identifiable":
  personal data of someone else. The exclusion's words, "personal data processed by an individual for any
  personal or domestic purpose", are not limited on their face to the user's own data. The same holds for
  payee names and UPI IDs inside bank alerts.

**Open:** The Act does not define "personal or domestic purpose". It does not say whether the exclusion
reaches the developer of a tool an individual runs, or whether data the user exports or shares (a split
summary sent to friends) stays "personal or domestic". Amendments after the 2023 Gazette text were not
checked (see section 2 for a reported 2026 order).

## 2. Digital Personal Data Protection Rules, 2025: notification and commencement

**Sources:**
- The Rules: G.S.R. 846(E), Gazette of India Extraordinary, Part II, Section 3(i), No. 760, 13 November 2025:
  https://www.meity.gov.in/static/uploads/2025/11/53450e6e5dc0bfa85ebd78686cadad39.pdf. Official.
- PIB backgrounder "DPDP Rules, 2025 Notified", 17 November 2025:
  https://static.pib.gov.in/WriteReadData/specificdocs/documents/2025/nov/doc20251117695301.pdf. Official.

**Quoted words:**
- Gazette: "NEW DELHI, THURSDAY, NOVEMBER 13, 2025"; "New Delhi, the 13th November, 2025 G.S.R. 846(E)".
- Rule 1: "(2) Rules 1, 2 and 17 to 21 shall come into force on the date of their publication in the Official
  Gazette. (3) Rule 4 shall come into force one year after the date of publication of this Gazette. (4) Rules
  3, 5 to 16, 22 and 23 shall come into force eighteen months after the date of publication of this
  Gazette."
- PIB: "DPDP Rules notified on 14 November 2025 after nationwide consultations." and "The Rules introduce an
  eighteen-month period for phased compliance."

**What it means for Memento:** Today, rules 1, 2 and 17 to 21 (the Board) are in force, and rule 4 (Consent
Managers) came into force in November 2026. Rules 3 and 5 to 16 come into force about May 2027: notice,
security safeguards, breach intimation, retention, contact details, children's consent, Significant Data
Fiduciaries, Data Principals' rights, transfer abroad. They are duties of a Data Fiduciary, so they reach
Memento only if the developer is one (section 1(b)).

**Open:**
- The Gazette is dated 13 November 2025 but PIB says "notified on 14 November 2025", so the 18-month date is
  13 or 14 May 2027.
- No official notification bringing the Act's own sections into force was found. Secondary (AZB & Partners,
  19 November 2025,
  https://www.azbpartners.com/bank/update-indias-digital-personal-data-protection-framework-comes-into-effect/):
  "Phase I – Effective November 13, 2025, the DPDP Act's institutional provisions"; "Phase II – After one
  year, i.e., on November 13, 2026, provisions relating to registration of consent managers"; "Phase III –
  The final phase, effective May 13, 2027, operationalizes the substantive framework".
- Secondary (India Briefing, 7 October 2026,
  https://www.india-briefing.com/news/dpdp-removal-of-difficulties-order-2026-consent-data-audit-47274.html/)
  reports "the Digital Personal Data Protection (Removal of Difficulties) Order 2026" and says "Sections 9
  and 10 are scheduled to come into effect on 13 March 2027". No official copy found; the date conflicts with
  the Rules' 18 months.

## 3. RBI Account Aggregator framework

**Source:** "Reserve Bank of India (Non-Banking Financial Companies - Account Aggregator) Directions, 2025",
RBI/DoR/2025-26/368, November 28, 2025: https://www.rbi.org.in/scripts/BS_ViewMasDirections.aspx?id=12936.
Official. They replace the 2016 Master Direction (para 61), so the 2016 text was not used.

**Quoted words:**
- Para 8(1): "‘Account Aggregator’ means a non-banking financial company as notified under in sub-clause (iii)
  of clause (f) of section 45-I of the Act, that undertakes the business of an account aggregator"
- Para 8(4): "‘business of an account aggregator’ means the business of providing under a contract, the
  service of, retrieving or collecting such financial information pertaining to its customer, as may be
  specified by the Reserve Bank from time to time; and consolidating, organizing and presenting such
  information to the customer or any other financial information user as may be specified by the Reserve
  Bank;"
- Para 8(10): "‘Financial Sector Regulator’ for the purpose of these directions, shall mean the Reserve Bank of
  India, Securities and Exchange Board of India, Insurance Regulatory and Development Authority of India,
  Pension Fund Regulatory and Development Authority and Department of Revenue, Ministry of Finance;"
- Para 8(12): "‘Financial Information User’ means an entity registered with and regulated by any financial
  sector regulator;"
- Para 11: "(1) No entity other than a company shall undertake the business of an Account Aggregator. (2) No
  company shall commence or carry on the business of an Account Aggregator without obtaining a certificate
  of registration from the Reserve Bank."
- Para 61: "With the issue of these Directions, the existing Directions, instructions, and guidelines relating
  to Non-Banking Financial Companies – Account Aggregators stand repealed"

**What it means for Memento:** Confirmed for the Account Aggregator route. A Financial Information User must be
"registered with and regulated by" a financial sector regulator, and an Account Aggregator must be a company
holding an RBI certificate. An individual developer is neither, so Memento cannot receive users' bank data
through the AA network. This governs any future "fetch from bank" feature.

**Open:** The Directions cover only the AA route and say nothing about other bank APIs, so "no bank API at all
without being regulated" is neither confirmed nor refuted here. They do not say whether data an AA presents
"to the customer" (para 8(4)) may then go into an app the user chooses. They do not address an app that parses
alerts on the user's own phone with no contract and no fetching from a Financial Information Provider.

## 4. RBI: banks' SMS alerts for electronic transactions

**Sources:** Official unless marked secondary.
- 2017 circular "Customer Protection – Limiting Liability of Customers in Unauthorised Electronic Banking
  Transactions", RBI/2017-18/15, July 6, 2017:
  https://www.rbi.org.in/Scripts/NotificationUser.aspx?Id=11040&Mode=0.
- "Reserve Bank of India (Commercial Banks - Responsible Business Conduct) Directions, 2025 (Updated as on
  October 1, 2026)", RBI/2025-26/170: https://www.rbi.org.in/Scripts/BS_ViewMasDirections.aspx?id=13140.
- "... (Commercial Banks - Responsible Business Conduct) Third Amendment Directions, 2026", RBI/2026-27/167,
  June 24, 2026: https://www.rbi.org.in/Scripts/NotificationUser.aspx?Id=13543&Mode=0; press release
  2026-2027/533: https://www.rbi.org.in/Scripts/BS_PressReleaseDisplay.aspx?prid=63011.
- Secondary: Whalesbook, 13 October 2025, on the banks' request:
  https://www.whalesbook.com/news/English/bankingfinance/Banks-Seek-RBI-Approval-to-Stop-SMS-Alerts-for-Transactions-Under-Rs-100/68ecc6ecda9cfbb49a24288b.
- Secondary: Business Today, May 29, 2024, on HDFC:
  https://www.businesstoday.in/industry/banks/story/hdfc-bank-to-stop-sms-alerts-for-upi-payments-up-to-rs-100-email-notifications-to-continue-431258-2024-05-29.
  HDFC's own InstaAlerts page (https://www.hdfc.bank.in/ways-to-bank/digital-banking/phone-banking/instaalerts)
  was read and does not state the UPI thresholds.

**Quoted words:**
- 2017 circular, para 5: "Banks must ask their customers to mandatorily register for SMS alerts and wherever
  available register for e-mail alerts, for electronic banking transactions. The SMS alerts shall mandatorily
  be sent to the customers, while email alerts may be sent, wherever registered."
- 2025 Directions, para 66 (the same words, in force today): "A bank shall ask its customers to mandatorily
  register for SMS alerts ... The SMS alerts shall mandatorily be sent to the customers, while email alerts
  may be sent, wherever registered."
- Third Amendment: "Instructions on ‘Limiting Liability of Customers in Unauthorised Electronic Banking
  Transactions’ for Commercial Banks (other than Small Finance Banks, Payments Banks, Regional Rural Banks,
  and Local Area Banks) ... have been consolidated in the Reserve Bank of India (Commercial Banks -
  Responsible Business Conduct) Directions, 2025."
- Para 3(2): "These Directions shall apply in cases of electronic banking transactions undertaken by customers
  of a bank on or after January 1, 2027."
- New para 76D: "A bank shall mandatorily send instant SMS alerts to its customers for all EBTs of value more
  than ₹500. For EBTs of value up to ₹500, a bank may decide to send instant SMS as per its internal policy but
  without any charge to the customer."
- New para 76E: "A bank shall send email alerts for all EBTs, wherever email address is provided by the
  customer."
- New para 76F: "SMS and email alerts as above shall be in addition to any other form of alerts, e.g., in-app /
  push notifications, instant messaging, etc., ... such transaction alerts shall contain relevant details
  pertaining to the EBT such as account / card number, amount, date, time, transaction channel, beneficiary /
  point of transaction, etc."
- New para 4(10D): "Electronic banking transaction (EBT) shall have the same meaning as ‘electronic funds
  transfer’ given in Section 2(c) of the Payment and Settlement Systems Act, 2007"
- Press release: "the Reserve Bank has today issued the following Amendment Directions, which shall come into
  effect from January 1, 2027."
- Secondary, Whalesbook: "Indian banks have formally approached the Reserve Bank of India (RBI)." The article
  says the aim is to end mandatory SMS alerts for payments of Rs 100 or less.
- Secondary, Business Today: "HDFC Bank will be stopping SMS alerts for UPI transactions below Rs 100 from June
  25, meaning customers will only receive text notifications for transactions above this amount or if they
  receive more than Rs 500 via UPI." and "Email alerts for all transactions will continue to be sent."

**What it means for Memento:** This governs capture. Until 31 December 2026, commercial banks must send an SMS
for every electronic transaction. From 1 January 2027, an SMS is mandatory only above ₹500; at or below ₹500
it is the bank's choice. Email alerts stay required "for all EBTs, wherever email address is provided". An
SMS-only reader will miss small transactions at banks that stop; email is the source the rule keeps complete.
Para 76F lists the fields an alert must carry, which is what the parser relies on.

**Open:** RBI's text does not link ₹500 to the banks' October 2025 request; the feedback annex that may do so
could not be read. Only the commercial-bank amendment was read: Small Finance, Payments, Regional Rural, Local
Area and co-operative banks have their own 2026 amendments. No source says which banks will stop SMS at or
below ₹500. HDFC's current UPI thresholds were not confirmed at HDFC's site. Whether every UPI payment is an
"EBT" rests on s.2(c) of the Payment and Settlement Systems Act, which was not read.

## 5. TRAI: commercial SMS headers, DLT and suffixes

**Sources:** All official.
- "Telecom Commercial Communications Customer Preference (Second Amendment) Regulations, 2025 (1 of 2025)",
  12 February 2025: https://www.trai.gov.in/sites/default/files/2025-02/Regulation_12022025.pdf.
- TRAI Press Release No. 11/2025, 12.02.2025, a scanned PDF read through its text layer:
  https://trai.gov.in/sites/default/files/2025-02/PR_No.11of2025.pdf.
- TRAI Direction F.No. D-2711/(2)/2024-QoS, November 18, 2025, on pre-tagging content-template variables:
  https://trai.gov.in/sites/default/files/2025-11/Directions_18112025_0.PDF.
- "... (Third Amendment) Regulations, 2026 (05 of 2026)", 18 September 2026:
  https://www.trai.gov.in/sites/default/files/2026-09/Regulation_18092026.pdf; press release:
  https://www.trai.gov.in/sites/default/files/2026-09/PR_No119of2026.pdf.

**Quoted words:**
- 2025 Regulations, new reg. 3(1): "Every Access Provider shall ensure that any commercial communication using
  its network takes place only using registered headers or the number resources allotted to the Senders from
  special series assigned for the purpose of commercial communication."
- Schedule item 2(1): "SMS Header for sending Transactional SMS, Service SMS, Promotional SMS and Government SMS
  from 11-character alphanumeric string, or as directed by the Authority, which are not allocated or assigned
  by DoT for other purposes: Provided that the type of Commercial Communication can be identified by
  Recipients from the Header structure or its format by suffixing "-P", "-S", "-T", and "-G" for Promotional,
  Service, Transactional, and Government Messages, respectively."
- Clause (bt): "“Transactional Message ...” means a Message sent ... by a Sender to its Customer or Subscriber
  in response to Customer initiated transaction within thirty minutes of the transaction relating to any
  product or service such as OTP from banks, ... transaction alerts and confirmations, balance alerts post
  completion of a transaction, refund information, etc."
- Clause (bh)(i): a Service Message is sent to "its Customer or Subscriber to provide information pertaining
  to any product or service, ... periodic balance alerts, ..."
- Explanatory Memorandum: "Adoption of Distributed Ledger Technology (DLT) has been mandated under the
  Regulations" and "any commercial communication can only take place using registered Headers assigned to the
  Senders".
- PR 11/2025, as printed: ""-F', "-S", "-T", and "-G" will be suffixed to the message header for
  identification of promotional, service, transactional, and government messages, respectively." The
  regulation itself says "-P".
- 2026 press release: "the Originating Access Provider shall suspend the misused Headers or Content Templates,
  within six hours of becoming aware of such misuse".

**What it means for Memento:** Genuine bank alerts come from a header the bank registered on the operators' DLT
platform. Transaction alerts sent within 30 minutes of a customer-initiated transaction are "Transactional"
("-T"); periodic balance alerts and similar are "Service" ("-S"); promotions are "-P". The suffix helps the
parser drop promotions and recognise alerts. It does not prove which bank sent a message, and TRAI's 2026 rules
exist because headers do get misused.

**Open:** The regulation fixes the suffixes, not the full displayed form (for example any operator or circle
prefix), and gives no list of which header belongs to which bank. It does not say whether a credit alert, which
the customer did not initiate, is "-T" or "-S". The roll-out date depends on the Gazette publication date ("after
thirty days"), which was not read. A search of the 2026 Third Amendment's OCR text layer found no change to the
suffix rule; OCR may have missed text.

## Not verified

- DPDP Act, India Code consolidated copy: 403, then 504. Amendments after the 11 August 2023 Gazette text were
  not checked.
- PIB press release PRID=2190014 (https://www.pib.gov.in/PressReleasePage.aspx?PRID=2190014): 403. The PIB
  backgrounder PDF was read instead.
- The official notification of which sections of the DPDP Act are in force: not found; secondary sources only.
- The "Digital Personal Data Protection (Removal of Difficulties) Order 2026" and a 13 March 2027 date: secondary
  report only.
- RBI's feedback annex of June 24, 2026 (https://rbidocs.rbi.org.in/rdocs/content/pdfs/Annex24062026FULL.pdf):
  bot check. RBI's answer to the banks' October 2025 request is not verified.
- The banks' October 2025 request: secondary source only.
- HDFC's 2024 thresholds (UPI debits under ₹100, credits up to ₹500): secondary only; HDFC's page does not state
  them, and its current practice was not confirmed.
- RBI's 2026 amendments for Small Finance, Payments, Regional Rural, Local Area and co-operative banks: not read.
- Payment and Settlement Systems Act, 2007, s.2(c), the meaning of "EBT": not read.
- The Gazette publication date of TRAI's 2025 regulation, and so the date the suffix rule took effect: not read.
