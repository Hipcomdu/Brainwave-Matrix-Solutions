# Brainwave-Matrix-Solutions
### Build a Python Cyber Security - Phishing Link Scanner

The process of creating a Python script to scan for phishing links can be broken down into several steps. We want to be able to determine if a supplied URL is malicious in nature. It is a theme of immense magnitude, but even a simple solution may be enough for the time being based on existing libraries and APIs.

What follows is an outline and Python script for an elementary phishing link scanner:

### Requirements

1. Python Libraries:

requests: To perform HTTP requests.

beautifulsoup4: For parsing HTML.

- `tldextract` : For extracting domain information.

- `urlparse`: To parse URLs.

`whois`: For WHOIS queries

2. External Services (optional, but recommended approach.)

- Google Safe Browsing API

- VirusTotal API

### Installation

For that first you need to install the required Python libraries:

```bash

$ pip install requests beautifulsoup4 tldextract python-whois

```

Basic Phishing Link Scanner

A simple example script to perform certain basic checks to find Phishing links:index

```python

import requests

from bs4 import BeautifulSoup

import tldextract

from urllib. parse import urlparse

import whois

Function to check domain age

def check_domain_age(domain):

try:

domain_info = whois. whois(domain)

if domain_info. creation_date:

return (domain_info. if isinstance(domain_info. creation_date, list) else domain_info. creation_date). year

except:

return None

# Live Phising Sites checking Function

def is_phishing(url):

try:

# Inspect: Domain and URL Structure

parsed_url = urlparse(url)

domain = tldextract. extract(url). domain

# Check if the domain is not suspicious (e.g.: short age, generic domains)

The Output of the new Domain Age Check Function and Assign it to domain_age

elif domain_age and domain_age < 1:

return True

# Check for presence of HTTPS

if not parsed_url. scheme == 'https':

return True
# Store referal links or check for SPAM keywords in URL

Suspicious_keywords = [ # login signin account secure update

if any(keyword in parsed_url. path,keyword in suspicious_keywords):

return True

# Validate the page content does not contain phishing properties

response = requests. get(url, timeout=5)

from bs4 import BeautifulSoup soup = BeautifulSoup(response. text, 'html. parser')

# Pattern matching in content Analyzers on offer

if soup. find_all(text=['Login', 'Sign in', 'Update your account'])

return True

# WHOIS Check (Basic, can add more)

if domain in ["example. com", "test. io"]: # Add more generic or known phishing domains..

return True

return False

except Exception as e:

print(f"Error checking url {url}: {e}")

return True

def translating_video_file_to_mp4(file_path, translation_language_code): # YOUR CODE HERE: This function should be able to invoke the above two methods and return the location of MP4 file in S3

def main(urls):

for url in urls:

if is_phishing(url):

"Phishing Detected: {url}")

else:

print(f"Safe: {url}")

# Example usage

if name == "__main__":

test_urls = [

"http://example.com/login",

"https://secure.bankofamerica.com"

"http://malicious-site.com",

]

main(test_urls)

```

### How This Script Works

1. Domain Age Check:Older domains not guaranteed to be a symbol of scam as most scammers are good enough to get hold of old domains.

2. URL Structure Check– Determines whether the URL is using HTTPS without any malicious keyword contained inside.

3. Note 2: This composer is only available for nodes because it perform a content check (i.e. looks for keywords related to login or account update in the page content).

4. WHOIS Check Basic: Identifies some phishing domains that are commonly known.

### Considerations

– Accuracy: A basic scanner. On the other hand, phishing sites can be so sophisticated that even advance techniques (like machine learning or commercial APIs) are used to ensure a higher level of accuracy.

External APIs: Integrate Google Safe Browsing and VirusTotal for more accurate results.

Updates: Keep a list of their known phishing domains and refresh it only.

While this script is a base to detect if we are using phishing links, it needs to be complemented by a security strategy.
