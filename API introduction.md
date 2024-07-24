API- Application  Programming Interface
- We use all the time.
- Eg: Booking OLA cab from Google  maps application
	- Map will communicate through API to OLA to request fare for the ride, availablity of cars.

- Above example is for API being shared externally, across organizations.
- Also powers internal apps, microsrrvices.
- Eg: If there is a authentication microservice in our organization, another developer can use that functionality API for their application.
- Power mobile and web application.
- Can be used to exposed to third parties, to trusted partners and customers who may integrate with our platform.

API communication:
-  Server-Server
- Between application and backends and so forth.

Consequences of API attack:
- In the case of Experian, credit card details of any user in US is exposed.
- In Bumble app, 100 million users exposed through a leaky API.
- In LinkedIn, everyone's infos are harvested via an API.
- In Venmo, 200 million transactions in full detail is harvested through a vulnerable API.


Why attakers target API:
- Direct access to sensitive data.
- Often "over-permissioned".
- Vulnerable to logic flaws.

# Real world breaches
1. Coinbase application (trading interface flaw)
- User scraped API calls from web UI.
- Identified 4 key parameters for any Coinbase transactions.
- Manipulated the parameters via API calls.
- Sold crypto they DID NOT own

2. USPS(United States Postal Service)
- USPS relied on  traditional code and web scanners.
- Found missing API authentication
- USPS added authentication.
- Left out authorization.
- User A able to access User B details (any of 60M accounts)

3. Peloton (Live streaming, real time performance tracking)
- Open API allowed requests for user details with NO authentication.
- 4M user account details exposed(including Joe Biden)
- Including accounts marked private.
- Researcher reported to Peloton.
- No response after 90 days.
- "Fixed" vulnerabiity by adding authentication.
- But hackers could still access all records, just needed to authenticate.

4. Venmo(payment platform)
- Venmo homepage presented live feed of transactions.
- hacker sinffed traffic and identified API calls.
- Wrote 20-line script, using 2 IP's
- Pulled 115k transactions/day - even with rate limiting placed.
- API returned ALL transaction details.
- 207M transactions harvestd.

5. Instagram
- Account reset requires 6-digit code
- Reasearcher found API to submit reset code guess.
- Guesses limited to 200 per IP.
- Researcher demonstrated could rotate through 5000 IPs in seconds.
- Enables takeover of any account.

6. Bumble
- API permitted access to 95M user account details without authentication.
- Incremental IDs allowed easy scraping of entire database.
- Enabled calculation of users' exact location via triangulation.
- API allowed paid features to be enabled without proper privileges.


7. Optus (Telecommunication company in Australia)
- API endpoint required no autentication to access.
- Attacker harvested 9.8M user details and threatened $1M ransom.
- Data included driver's license, Medicare IDs,  name, phone, email.

8. Experian (credit reporting agency)
- Experian partner site offered loan elegibility feature.
- Feature used Experian API for lenders to automate credit score lookup.
- Attacker sniffed API calls.
- API accessible with no authentication.
- Results delivered with name, address and *any* value for DOB.


# 3 Pillars of API security
	1.Governance - Developing secure APIs
	2.Testing - Ensuring APIs are free of flaws
	3.Monitoring - Detecting threats in production




# Tips and Tricks:

Google: try advanced searches to discover API information, for example:
- inurl:"/wp-json/wp/v2/users" - Finds all publicly available WordPress API user directories.
- intitle:"index.of" intext:"api.txt" - Finds publicly available API key files.
- inurl:"/api/v1" intext:"index of /" - Finds potentially interesting API directories.
- ext:php inurl:"api.php?action=" - Finds all sites with a XenAPI SQL injection vulnerability.
- intitle:"index of" api_key OR "api key" OR apiKey -pool - This lists potentially exposed API keys.