# How it works

1. **Create.** The browser uploads files or text to the API. Metadata goes to PostgreSQL, and file bytes go to S3-compatible object storage.
2. **Share.** The creator gets a short code, a link and a QR code, plus a private management token that stays in their browser.
3. **Receive.** The other device enters the code. The server checks the expiry and the password, then serves the files through an authenticated download.
4. **Live Drop.** Guests request to join and the host approves each one. Messages and files are saved through the API first, then broadcast over WebSockets.
5. **Expire.** A background sweep deletes expired Drops and their files. A storage lifecycle rule acts as a backstop.
