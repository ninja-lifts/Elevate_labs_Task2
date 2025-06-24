# Phishing Analysis Report

## 1. Sender's Email Address Analysis
The sender's address is designed to look legitimate but is a major red flag.

**Display Name:** "Microsoft Support" is used to build trust.

**Actual Email Address:** `<security-alert@microsoft-support-team.com>`

**Phishing Indicator:** Legitimate Microsoft emails come from official domains like `@microsoft.com`, `@account.microsoft.com`, or `@microsoftsupport.com`. The domain `microsoft-support-team.com` is a lookalike domain, likely registered by attackers to deceive recipients.

## 2. Email Header Analysis
To analyze the headers, you would copy the full email headers (often found under an option like "Show Original" or "View Source") and paste them into a header analyzer tool (like the one from MXToolBox). The tool would reveal the following discrepancies:

**Received: Path:** The Received headers trace the email's journey from sender to receiver. In this case, the headers would show the email originated from a server like `mail.random-hosting.co` and not from Microsoft's known mail servers (e.g., `outlook.com`).

**Authentication-Results (SPF & DKIM):**
- **SPF (Sender Policy Framework):** The analyzer would show `spf=fail`. This means the server at `microsoft-support-team.com` is not authorized to send emails on behalf of Microsoft.
- **DKIM (DomainKeys Identified Mail):** The analyzer would likely show `dkim=fail` or `dkim=none`. This indicates the email lacks a valid digital signature to prove it came from the stated domain.

**Reply-To: Field:** Sometimes, a phisher will set a different Reply-To address (e.g., `phisher-inbox@gmail.com`) so that if you accidentally reply, the message goes directly to them instead of the spoofed address.

## 3. Suspicious Links and Mismatched URLs
This is one of the most reliable ways to spot a phishing attempt.

**Link Text:** The email displays a clickable link with the text "Verify Your Account Now."

**Actual Destination (Hover URL):** When you hover your mouse over the link without clicking, the browser or email client reveals the true destination: `http://m1crosoft-login-auth.xyz/...`

**Phishing Indicators:**
- **Mismatched URL:** The displayed text and the actual link do not match.
- **Deceptive Domain:** The domain `m1crosoft-login-auth.xyz` is clearly not an official Microsoft domain. It uses "m1crosoft" (with a "1" instead of an "i") and a non-standard Top-Level Domain (`.xyz`) to trick users.
- **Insecure Protocol:** The link uses `http://` instead of the secure `https://`. A legitimate login page will always use HTTPS for encryption.

## 4. Urgent and Threatening Language
The email's body is crafted to create panic and bypass rational thinking.

**Urgency:** Phrases like "URGENT", "Action Required", and "immediately" pressure the user to act quickly.

**Threat:** The email contains a clear threat: "Failure to do so within 24 hours will result in permanent account suspension." This scare tactic is designed to make the recipient click the link without thinking.

## 5. Spelling and Grammar Errors
While some phishing emails are perfectly written, many contain subtle errors that a large, professional corporation like Microsoft would not make.

- **sign in vs. sign-in:** "unusual sign in" should be hyphenated as a noun ("sign-in").
- **unrecognised:** While this is the British spelling, large US companies like Microsoft typically use American English ("unrecognized"). This inconsistency can be a red flag.
- **you're vs. your:** The email says, "...security of you're account...". This is a grammatical error; it should be "your account."
- **bellow vs. below:** The email says, "...link bellow...". The correct spelling is "below."
