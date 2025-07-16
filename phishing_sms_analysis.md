# Phishing SMS Analysis – Apple Support Scam (Detailed Breakdown)

This document provides a technical breakdown of a real phishing SMS message impersonating Apple Support. It includes red flag indicators, attacker objectives, recommended SOC responses, and security framework mapping.

---

## 🧾 Message Contents

> **Apple Account Security Alert**  
> We have detected unusual activity on your Apple ID associated with a transaction at “Apple Store - CA” for $143.95...  
> Call Apple Support: +1804xxxxxxx  
> Visit: https://support.apple.com/billing

---

## 🚩 Indicators of Phishing

| Indicator                            | Explanation                                                                 |
|-------------------------------------|-----------------------------------------------------------------------------|
| Urgent tone                         | “Failure to act promptly...” → pressure to scare the victim                |
| Impersonated sender                 | Claims to be Apple Support, but not verified or signed message             |
| Suspicious phone number             | No Apple messages include support numbers like this                        |
| Link spoofing                       | URL appears legit but may be a masked redirect to a phishing page          |
| Generic structure                   | No personalization, vague threat, grammar issues                           |

---

## 🎯 Attacker Objectives

The attacker likely aims to:
- Trick victims into calling a fake number (vishing)
- Direct them to a spoofed Apple login page (credential harvesting)
- Possibly collect credit card or Apple ID credentials
- Push for remote access or further scam activity

---

## 🧠 SOC Analyst Response

If received on a work device or by an employee:

1. **Initial Classification**: Phishing – SMS-based (Smishing)
2. **Triage Priority**: Medium – escalate if user interacted
3. **Immediate Actions**:
   - Block phone number
   - Add link/number to threat intel feeds
   - Notify IT and affected user(s)
   - Educate employees on scam format

4. **Optional SIEM Rule**:
5. rule: “Suspicious SMS claiming Apple Support”
condition: message contains “Apple Pay” AND “Call Apple Support”
severity: medium

---

## 🧭 MITRE ATT&CK Mapping

| Technique ID | Technique Name                  | Description                              |
|--------------|----------------------------------|------------------------------------------|
| T1566.001    | Phishing: Spearphishing via Service | Message sent via iMessage (SMS-based)    |
| T1586        | Compromise Accounts             | Attempts to steal Apple ID credentials   |
| T1598.003    | Phishing for Information        | Seeks user interaction and verification  |
| T1110.001    | Brute Force: Credential Stuffing | If credentials are reused or tested later|

---

## 🧠 Lessons for Analysts

- Even well-crafted phishing SMS messages often include subtle giveaways
- Training users to recognize smishing attacks is just as important as email phishing
- Attacks like these can be used as awareness material and case studies in threat detection programs

---

## 📂 Related Files

- `README.md` – Project overview
- `apple_phishing_sms.jpg` – Scam screenshot
