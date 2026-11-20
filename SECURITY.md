# Security

## Reporting a problem

If you find a security issue in LG Remote, please **do not open a public issue**.
Use GitHub's private reporting instead: **Security → Report a vulnerability** on this repository.
You'll get a reply as soon as possible, and a fix will be released before the details are made public.

## What the app can and cannot do

- The app requires INTERNET permission to communicate with your LG TV over your local WiFi network.
- No data leaves your local network: the app only sends LG's webOS control commands to the TV IP address you enter.
- No analytics, no tracking, no cloud services.

## Release signing

- Releases are built and signed by GitHub Actions. The signing key is stored only in encrypted GitHub Secrets, is unpacked only for the signing step and deleted right after. It is not in this repository or its history.
