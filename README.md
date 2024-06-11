# mitmproxy redirector
With this script you can redirect only spesific HTTP and Websocket requests of your web browser to your local (or any other) web applications.

This script can be run only with user priviliges. Mitmproxy has standalone executables for all OSes.

## Usage

- ### Certificate

Add $HOME/.mitmproxy/mitmproxy-ca-cert.cert file to web browser (only current browser profile is enough). This certificate file is creating after the first run of mitmproxy.

For Firefox:
- Settings
- View Certificates
- Authorities
- Import
- Choose $HOME/.mitmproxy/mitmproxy-ca-cert.cert file only.

OS based certificate formats exist. Read this: https://docs.mitmproxy.org/stable/concepts-certificates/#the-mitmproxy-certificate-authority

- ### Defining the proxy to web browser

Add proxy for http and https: localhost:44700

- ### Run mitmproxy

Linux

> ./mitmweb -s mitm-redirect-url.py --listen-port 44700

MS Windows

> mitmweb.exe -s mitm-redirect-url.py --listen-port 44700

- ### Ignore CORS (Optional)

Optionally you can ignore CORS for your current browser profile. You can use below extension for Firefox:

https://addons.mozilla.org/en-US/firefox/addon/cors-everywhere/
