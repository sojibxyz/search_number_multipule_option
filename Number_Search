import requests
from bs4 import BeautifulSoup

def search_google(phone_number):
    google_url = f"https://www.google.com/search?q={phone_number}"

    headers = {"User-Agent":"Mozilla/5.0(Windows NT 10.0; Win64;x64) AppleWebkit/537.36 (KHTML,like Gecko) Chrome/91.0.4472.124 safari/537.36"}
    response = requests.get(google_url,headers=headers)
    soup= BeautifulSoup(response.text,"html.parser")

    results = []
    for link in soup.find_all('a'):
        href = link.get('href')
        if href and "http" in href:
            results.append(href)
    return list(set(results))

def search_bing(phone_number):
    bing_url = f"https://www.bing.com/search?q={phone_number}"
    headers = {
        "User-Agent": "Mozilla/5.0(Windows NT 10.0; Win64;x64) AppleWebkit/537.36 (KHTML,like Gecko) Chrome/91.0.4472.124 safari/537.36"}
    response = requests.get(bing_url, headers=headers)
    soup = BeautifulSoup(response.text,"html.parser")

    results =[]
    for link in soup.find_all("a"):
        href = link.get("href")
        if href and "http" in href:
            results.append(href)
    return list(set(results))

def search_linkedin(phone_number):
    linkedin_url = f'https://www.linkedin.com/search/results/all/?keywords={phone_number}'
    headers = {
        "User-Agent": "Mozilla/5.0(Windows NT 10.0; Win64;x64) AppleWebkit/537.36 (KHTML,like Gecko) Chrome/91.0.4472.124 safari/537.36"}
    response = requests.get(linkedin_url, headers=headers)
    soup = BeautifulSoup(response.text, "html.parser")

    results = []
    for link in soup.find_all("a"):
        href = link.get("href")
        if href and "http" in href:
            results.append(href)
    return list(set(results))

def facebook_search(phone_number):
    facebook_url = f"https://www.facebook.com/search/top?q={phone_number}"
    headers = {
        "User-Agent": "Mozilla/5.0(Windows NT 10.0; Win64;x64) AppleWebkit/537.36 (KHTML,like Gecko) Chrome/91.0.4472.124 safari/537.36"}
    response = requests.get(facebook_url, headers=headers)
    soup = BeautifulSoup(response.text, "html.parser")

    results = []
    for link in soup.find_all("a"):
        href = link.get("href")
        if href and "http" in href:
            results.append(href)
    return list(set(results))

def phone_number_lookup(phone_number):
    print(f"Searching for phone number: {phone_number}")

# Google search
    print("\n[+] Searching on google....")
    google_results = search_google(phone_number)

    print("\n".join(google_results[:10]))
# Display top 10 results

# bing search
    print("\n[+] searching on Bing....")
    bing_results=search_bing(phone_number)

    print("\n".join(bing_results[:10]))
    # Display top 10 result

    # linkedin search

    print("\n[+] searching on Linkedin.....")
    linkedin_results = search_linkedin(phone_number)

    print("\n".join(linkedin_results[:10]))

    # Display top 10 number

    # facebook search
    print("\n[+1] searching on facebook,,,,,")
    facebook_results= facebook_search(phone_number)

    print("\n".join(facebook_results[:10]))

phone_number = input("Enter a phone number:")
phone_number_lookup(phone_number)
