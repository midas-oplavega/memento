# Licences

What the licences of the code Memento may take in allow, against its own
licence, AGPL-3.0-or-later, and the licences of what it already builds on.
All sources were read on 2026-11-25. Each section quotes the words its finding
rests on, says what it may mean for Memento, and names what the source leaves
open. This is not legal advice.

## 1. Licences and their compatibility

**Sources:**
- FSF, "Various Licenses and Comments about Them" (page "$Date: 2026/04/22"):
  https://www.gnu.org/licenses/license-list.html. Official.
- choosealicense.com appendix (https://choosealicense.com/appendix/) and AGPL-3.0 page, which reproduces the
  licence text (https://choosealicense.com/licenses/agpl-3.0/). Secondary to the FSF, the licence's steward.
- FSF, "GPL Enforcement in Apple's App Store", May 25, 2010: https://www.fsf.org/news/2010-05-app-store-compliance.
- Brett Smith (FSF), "More about the App Store GPL Enforcement", May 26, 2010:
  https://www.fsf.org/blogs/licensing/more-about-the-app-store-gpl-enforcement.
- Bradley M. Kuhn (FSF blog), "Left wondering why VLC relicensed some code to LGPL", Nov 29, 2012:
  https://www.fsf.org/blogs/licensing/left-wondering-why-vlc-relicensed-some-code-to-lgpl.

**Quoted words, FSF list:**

| Licence | FSF's words |
|---|---|
| Expat ("MIT") | "a lax, permissive non-copyleft free software license, compatible with the GNU GPL." |
| BSD-3-Clause (Modified BSD) | "a lax, permissive non-copyleft free software license, compatible with the GNU GPL." "sometimes referred to as the 3-clause BSD license." |
| BSD-2-Clause (FreeBSD) | "(It is also sometimes called the “2-clause BSD license”.) It is a lax, permissive non-copyleft free software license, compatible with the GNU GPL." |
| Apache-2.0 | "This is a free software license, compatible with version 3 of the GNU GPL. Please note that this license is not compatible with GPL version 2" |
| MPL-2.0 | "Section 3.3 provides indirect compatibility between this license and the GNU GPL version 2.0, the GNU LGPL version 2.1, the GNU AGPL version 3, and all later versions of those licenses." But: "Parties who release original work under MPL 2.0 may choose to opt out of this compatibility by including a sentence in the license notices that says that the work is “Incompatible With Secondary Licenses.” Any software that includes this notice is not compatible with the GPL or AGPL." |
| LGPL-2.1 | "It is compatible with GPLv2 and GPLv3." |
| LGPL-3.0 | "It is compatible with GPLv3." |
| ISC | "It is a free software license, and compatible with the GNU GPL." |
| zlib | "This is a free software license, and compatible with the GPL." |
| CC0 | "Both public domain works and the lax license provided by CC0 are compatible with the GNU GPL." Also: "For works of software it is not recommended, as CC0 has a term expressly stating it does not grant you any patent licenses." |
| Unlicense | "Both public domain works and the lax license provided by the Unlicense are compatible with the GNU GPL." |
| Public domain | "Public domain material is compatible with the GNU GPL." |

The AGPL entry, on AGPLv3 and GPLv3: "you are allowed to combine separate modules or source files released under
both of those licenses in a single project".

**Quoted words, choosealicense and the AGPL text:**
- "Disclose source": "Source code must be made available when the licensed material is distributed."
- "Same license": "Modifications must be released under the same license when distributing the licensed
  material. In some cases a similar or related license may be used."
- "Network use is distribution": "Users who interact with the licensed material via network are given the right
  to receive a copy of the source code."
- The AGPL-3.0 page lists all three among its Conditions, with "License and copyright notice" and "State
  changes".
- AGPLv3 s.13: "if you modify the Program, your modified version must prominently offer all users interacting
  with it remotely through a computer network (if your version supports such interaction) an opportunity to
  receive the Corresponding Source".
- AGPLv3 s.10: "You may not impose any further restrictions on the exercise of the rights granted or affirmed
  under this License."
- AGPLv3 s.7: "“Additional permissions” are terms that supplement the terms of this License by making exceptions
  from one or more of its conditions."

**Quoted words, FSF on app stores:**
- 2010 news: "Apple imposes numerous legal restrictions on use and distribution of GNU Go through the iTunes
  Store Terms of Service, which is forbidden by section 6 of GPLv2." and "instead of amending their terms of
  service to work with the GNU GPL, Apple have decided to remove GNU Go from the App Store."
- Smith: "this analysis would apply to all versions of the GNU GPL and AGPL." "the Usage Rules are imposed on you
  no matter how the software is licensed." "Apple's Terms of Service impose restrictive limits on use and
  distribution for any software distributed through the App Store, and the GPL doesn't allow that."
- Kuhn: "those incompatibilities still exist with the LGPL or, indeed, any true copyleft license. The
  incompatibilities of Apple's terms are so strict that they make it absolutely impossible to comply
  simultaneously with any copyleft and Apple's terms at the same time. Other similar terms aren't much better,
  even with Google's Play Store (— its terms are incompatible with any copyleft license if the project has many
  copyright holders)."

**What it means for Memento:**
- *Dependencies.* Every licence asked about is GPL-compatible in the FSF's words. MPL-2.0 is compatible unless
  its notice says "Incompatible With Secondary Licenses"; Apache-2.0 only with GPLv3, which suits AGPLv3+. The
  check is each dependency's notice, not its licence name.
- *Copyleft duties.* Distributing the APK carries "disclose source" and "same license". The network clause
  (s.13) applies to a modified version users reach "remotely through a computer network"; with no server it
  does not arise unless one is added.
- *App stores.* On the FSF's reading, the conflict is a breach of the licence's no-further-restrictions term,
  which only a licensor can enforce. A sole copyright holder licenses their own code and can add an s.7
  "additional permission". Code taken in from others under GPL/AGPL stays bound by its holders' terms, so on
  the FSF's reading it cannot ship through Apple's store without their permission. This governs the planned
  iOS release and contributions accepted from others.

**Open:**
- None of the FSF statements read says in words that a sole copyright holder may publish their own AGPL code
  on the App Store, or that an s.7 permission cures the conflict. That inference is ours. The GPL FAQ, which
  may address it, could not be read.
- The posts quote Apple's 2010 terms; the current terms were not read.
- Kuhn's Google Play remark ("if the project has many copyright holders") is unexplained, and Google's current
  terms were not read. It bears on the Android release and on outside contributions.
- The FSF list states compatibility "with the GNU GPL"; only the MPL-2.0 entry names AGPLv3. That the same holds
  for AGPLv3 rests on the AGPL entry's combination clause.

## 2. Licences of Flutter, drift and SQLite

**Sources:** All official.
- Flutter: https://github.com/flutter/flutter/blob/master/LICENSE, plus GitHub's licence API for
  flutter/flutter.
- drift: https://pub.dev/packages/drift (version 2.35.4, "Published 16 days ago • simonbinder.eu") and
  https://pub.dev/packages/drift/license.
- SQLite: https://sqlite.org/copyright.html. SPDX: https://spdx.org/licenses/blessing.html.

**Quoted words:**
- Flutter: "Copyright 2014 The Flutter Authors. All rights reserved. Redistribution and use in source and binary
  forms, with or without modification, are permitted provided that the following conditions are met:" The text
  gives three conditions, the third "Neither the name of Google Inc. nor the names of its contributors may be
  used to endorse or promote products". GitHub's API reports `spdx_id` "BSD-3-Clause".
- drift: pub.dev shows "License MIT (license)"; the licence file begins "MIT License Copyright (c) 2021 Simon
  Binder Permission is hereby granted, free of charge, ...". Dependencies: "async, collection, convert, meta,
  path, sqlite3, stack_trace, stream_channel, web".
- SQLite: "All of the code and documentation in SQLite has been dedicated to the public domain by the authors."
  "Anyone is free to copy, modify, publish, use, compile, sell, or distribute the original SQLite code, either
  in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means."
- SPDX: "SQLite Blessing", short identifier "blessing", for the source-file text "The author disclaims
  copyright to this source code. In place of a legal notice, here is a blessing:".

**What it means for Memento:** Flutter is BSD-3-Clause, drift is MIT (Expat), and SQLite is public domain. The
SQLite copyright page gives no SPDX ID; "blessing" is the SPDX ID of its source-file notice. All three are
GPL-compatible per the FSF list (section 1). They govern the app's framework and storage layer.

**Open:** A Flutter build also bundles the Flutter engine and its third-party components, whose licences were not
checked. drift's `sqlite3` dependency and any native SQLite bundling package were not checked. Every other
package Memento adds needs its own check.

## Not verified

- The GNU GPL FAQ (https://www.gnu.org/licenses/gpl-faq.html): timed out twice.
- Apple's and Google's current store terms: not read.
- Licences of the Flutter engine's bundled components and of drift's dependencies: not checked.
