# Security and permission boundaries

1. **Do not commit secrets**: API keys, bearer tokens, cookies, passwords, private customer information, access URLs, or screenshots with credentials.
2. Different bots in the same Grok Bot account may share a cloud-computer environment. **Do not treat separate bots as a security boundary.** Check current official docs and your account settings.
3. Use least privilege and service-specific credentials. Never place credentials inside prompt text or this repository.
4. Gate publication, purchases, sending external messages, deletion, and production modifications behind explicit approvals.
5. A prompt does not enforce real quota or retry budgets. Use platform settings, application logic, idempotency keys, and monitoring when hard controls are required.
6. Audit third-party skills before adapting them. Do not automatically execute arbitrary scripts or assume paths like `/home/box/...` exist.
7. Review repository contents, filenames, commit history, and README before making a repository public. Publishing an existing private repo exposes its history too.
