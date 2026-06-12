
### 🗄️ Data Collection Methods

---

#### 1. **Web Scraping** _(Automated)_

- Use **Python + BeautifulSoup / Scrapy** to extract scholarship listings from websites
- Best for sites without APIs like ScholarshipTab, Opportunity Desk, Scholars4Dev
- Schedule scrapers to run daily or weekly via **cron jobs**
- Extract fields: title, deadline, country, funding type, field of study, link

python

```python
# Basic example
import requests
from bs4 import BeautifulSoup

url = "https://www.scholars4dev.com/"
soup = BeautifulSoup(requests.get(url).text, "html.parser")
scholarships = soup.find_all("article")
```

**Limitations:** breaks when sites redesign; some block scrapers

---

#### 2. **RSS Feeds** _(Free & Reliable)_

Many scholarship sites publish RSS feeds — easiest freshness method

- `opportunitydesk.org/feed`
- `scholars4dev.com/feed`
- `reliefweb.int/updates/feed`

Parse with **Python feedparser** — no scraping needed, updates automatically

---

#### 3. **Official APIs** _(Most Reliable)_

Some platforms offer structured data access

- **UNHCR** — has data APIs for humanitarian programs
- **Mastersportal** — offers partner API access
- **ReliefWeb** — has a free public API `api.reliefweb.int`
- **DAAD** — structured data available for partners

---

#### 4. **Email Alerts + Parsing** _(Semi-Automated)_

- Subscribe to email alerts from all platforms
- Use **Gmail API + Python** to auto-parse incoming scholarship emails
- Extract structured data and push to your database

---

#### 5. **Manual Curation** _(For Refugee-Specific Data)_

For fields no scraper can extract — like _"accepts UNHCR docs"_ or _"conflict-affected eligible"_ — you need human reviewers to tag entries manually

- Build a simple admin panel for volunteers or staff to tag and verify
- Partner with UNHCR field offices for ground-truth data

---

### 🔄 Keeping Data Fresh

---

#### Freshness Strategy by Source Type

| Source             | Method                 | Frequency     |
| ------------------ | ---------------------- | ------------- |
| RSS feeds          | Auto-parse             | Every 6 hours |
| Scraped sites      | Scheduled scraper      | Daily         |
| Official APIs      | API polling            | Daily         |
| Email alerts       | Gmail parser           | Real-time     |
| Manual entries     | Admin review           | Weekly        |
| Government portals | Scraper + manual check | Weekly        |
