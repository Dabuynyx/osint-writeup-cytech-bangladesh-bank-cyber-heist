# Bangladesh Bank Cyber Heist — Cytech CTF Write-Up

| Challenge | Category | Final Flag |
| :--- | :--- | :--- |
| **Bangladesh Bank Cyber Heist** | OSINT / Cyber Threat Intelligence | `Cryptix{fandation_Jupiter_ChosunExpoJointVenture_90}` |

---

## 📌 Challenge Overview

This challenge investigates the infamous **2016 Bangladesh Bank cyber heist** orchestrated by North Korea's state-sponsored group (Lazarus Group / APT38). The objective is to research public records, news disclosures, and DOJ court dockets to answer four specific investigative questions and reconstruct the flag.

**Flag Format:**
```text
Cryptix{<Answer1>_<Answer2>_<Answer3>_<Answer4>}
```

---

## 🔍 Step-by-Step Questions & Investigation

### Question 1: The Misspelled Word

> **Prompt:** *What was the misspelled word, exactly as the thieves wrote it?*

#### Investigation:
* **Search queries:** `"Bangladesh Bank heist" "typo"` / `"misspelled"`
* The attackers issued fraudulent SWIFT payment orders seeking to siphon nearly $1 billion from Bangladesh Bank's account at the Federal Reserve Bank of New York.
* One instruction for $20 million was destined for a fictitious Sri Lankan NGO named the **Shalika Foundation**.
* The attackers misspelled **"foundation"** as **"fandation"**.
* Routing bank Deutsche Bank noticed the spelling anomaly and halted the processing for manual verification, triggering an alarm that prevented the theft of hundreds of millions more.

**Answer 1:**
```text
fandation
```

---

### Question 2: The Destination Bank Branch

> **Prompt:** *Most of the stolen money landed in one bank branch in another country. That branch is named after a street, and that street is named after a planet. Which planet?*

#### Investigation:
* **Search queries:** `"Bangladesh Bank heist" "branch" "$81 million" "street"`
* While several transactions were blocked, **$81 million** successfully routed to the Philippines into accounts at **Rizal Commercial Banking Corporation (RCBC)**.
* The branch involved was located on **Jupiter Street** in Makati City, Metro Manila.
* The street is named after the planet **Jupiter**.

**Answer 2:**
```text
Jupiter
```

---

### Question 3: The Front Company Alias

> **Prompt:** *Years later, a man was charged for his role. Investigators say he worked for a company that used two names. Bring us the one that doesn’t carry the country’s common name. (no spaces)*

#### Investigation:
* **Search queries:** `"Bangladesh Bank heist" "charged" "DOJ" "company"`
* In 2018, the United States Department of Justice filed federal charges against North Korean hacker **Park Jin Hyok** (Lazarus Group / APT38).
* According to the DOJ criminal complaint, Park worked under cover of a state-backed front company operating under two names:
  1. **Korea Expo Joint Venture** (KEJV)
  2. **Chosun Expo Joint Venture**
* *"Korea"* is the country's common international name, while *"Chosun"* represents the traditional Korean name.
* Removing spaces per the challenge requirements: `ChosunExpoJointVenture`.

**Answer 3:**
```text
ChosunExpoJointVenture
```

---

### Question 4: Sealed Days Calculation

> **Prompt:** *The charges against him were filed in secret, then revealed to the world. How many days were they hidden?*

#### Investigation:
* **Court Docket:** *United States v. Park Jin Hyok* (U.S. District Court, Central District of California / CourtListener Docket 7833295)
* **Date Filed Under Seal:** June 8, 2018
* **Date Unsealed / Made Public:** September 6, 2018
* **Day Count Calculation:**
  * June 8 → June 30: $30 - 8 = 22$ days
  * July: 31 days
  * August: 31 days
  * September 1 → September 6: 6 days
  * **Total:** $22 + 31 + 31 + 6 = 90\text{ days}$
  *(Or: June 8 → July 8 = 30 days, July 8 → August 8 = 31 days, August 8 → September 6 = 29 days = 90 days)*

**Answer 4:**
```text
90
```

---

## 🚩 Flag Construction

Combine all four answers with underscores:
* **Answer 1:** `fandation`
* **Answer 2:** `Jupiter`
* **Answer 3:** `ChosunExpoJointVenture`
* **Answer 4:** `90`

```text
Cryptix{fandation_Jupiter_ChosunExpoJointVenture_90}
```

---

## 📚 Primary Sources & References

* [Wikipedia — Bangladesh Bank robbery](https://en.wikipedia.org/wiki/Bangladesh_Bank_robbery)
* [Reuters — How a hacker's typo helped stop a billion-dollar bank heist](https://www.reuters.com/article/us-usa-fed-bangladesh-typo-insight/how-a-hackers-typo-helped-stop-a-billion-dollar-bank-heist-idUSKCN0WC0TC/)
* [U.S. Department of Justice — North Korean Regime-Backed Programmer Charged](https://www.justice.gov/usao-cdca/pr/north-korean-regime-backed-programmer-charged-conspiracy-conduct-multiple-cyberattacks)
* [CourtListener Docket — United States v. Hyok](https://www.courtlistener.com/docket/7833295/united-states-v-hyok/)
* [FBI Cyber Wanted — Park Jin Hyok](https://www.fbi.gov/wanted/cyber/park-jin-hyok)
