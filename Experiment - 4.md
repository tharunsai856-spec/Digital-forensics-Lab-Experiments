# Experiment 4: Analyze Email Headers and Detect Email Spoofing using MHA (Mail Header Analyzer)

## Aim
The primary aim of this experiment is to detect email spoofing by meticulously analyzing email headers. By using a specialized tool like the Microsoft Message Header Analyzer (MHA), we can decode the raw header information to identify inconsistencies, forged details, and authentication failures that signal a fraudulent email.

## Description
Email headers are a hidden digital trail that documents an email's journey from sender to recipient. They contain critical metadata, including the servers the message passed through, timestamps, and authentication results. A spoofed email is one where the "From" address is faked to appear as though it's from a legitimate source, like a trusted company or colleague. Attackers do this to trick recipients into revealing sensitive information or taking harmful actions. MHA is an online tool that parses this complex, raw header data into a human-readable format, making it easy to identify key red flags such as a mismatch between the visible sender and the true sending server, or a failed SPF, DKIM, or DMARC authentication check.

## Tools & Equipment Used
A computer with a web browser.

An email client (e.g., Gmail, Outlook, etc.) to access the email with the suspicious headers.

The MHA (Message Header Analyzer) tool: A free, web-based tool provided by Microsoft, accessible at mha.azurewebsites.net.

## Procedure
Retrieve the Email Header: Open the suspicious email in your email client. The process for viewing the full header varies by client, but it's usually found in a "View original," "Show original," or "Message properties" option within a dropdown menu. Copy the entire block of raw text, from the first "Received" line to the end.
![alt text](<Screenshot2/Screenshot 2025-09-02 160918.png>)

Paste into MHA: Navigate to the MHA website. Paste the entire copied header text into the designated input box on the page.
![alt text](<Screenshot2/Screenshot 2025-09-02 160955.png>)

Analyze the Header: Click the "Analyze headers" button. MHA will process the raw data and present it in a clear, organized format with multiple sections.
![alt text](<Screenshot2/Screenshot 2025-09-02 161008.png>)

Examine for Spoofing Indicators: The key to this experiment is to inspect the output for signs of a fraudulent email. Look for:
![alt text](<Screenshot2/Screenshot 2025-09-02 161143.png>)

Mismatching "From" and "Return-Path" Addresses: Check the "Received" section. The first Received line often shows the true origin server. Compare the domain of this server with the domain of the visible sender in the "From" field. A mismatch is a major red flag. Also, check the "Return-Path" and "Reply-To" headers; if they differ from the "From" address, it's a strong sign of spoofing.
![alt text](<Screenshot2/Screenshot 2025-09-02 161249.png>)

Authentication Results: Look for the "Authentication-Results" header. This section reports on checks like SPF (Sender Policy Framework), DKIM (DomainKeys Identified Mail), and DMARC (Domain-based Message Authentication, Reporting and Conformance). If any of these show a "Fail" or "SoftFail", it means the email failed a crucial test and is likely forged. A failed SPF check, for example, means the email did not originate from a server authorized to send emails for that domain.
![alt text](<Screenshot2/Screenshot 2025-09-02 161301.png>)

## Result
The experiment is successful when MHA's analysis of the email headers reveals clear discrepancies that would be difficult to spot manually. For instance, the MHA's "Received" tab might visually map the email's hop-by-hop journey, showing an originating server IP address located in a different country than the supposed sender. The "Authentication-Results" section would clearly display a "Fail" verdict for SPF or DKIM, providing definitive evidence of a forged sender. The results demonstrate that email spoofing can be reliably detected by going beyond the visible "From" field and examining the underlying headers. MHA's ability to simplify this process makes it an indispensable tool for both network administrators and end-users in identifying and avoiding phishing attacks.