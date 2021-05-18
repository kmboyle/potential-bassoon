# Introduction
<a href="https://taxcloud.com" target="_blank">TaxCloud</a> is the internet's only free sales tax compliance service. We can provide TaxCloud at no cost to retailers because we are paid by the states to make sales tax compliance as easy as possible—it's just that simple.

OK, it is a little more complicated than that, but that is our goal. TaxCloud has achieved Certified Service Provider designation in 25 states. These "Member States" pay for our service so filers into these states don’t have to. There are another 20 states that collect sales and use tax, and our TaxCloud API supports accurate tax determination in those states as well. However, the filers themselves pay TaxCloud for the transactions into these states that have not yet enacted provisions for certification.

## The TaxCloud API
The TaxCloud API is organized around Representational State Transfer (REST). Our API has predictable resource oriented endpoints, accepts form encoded request bodies, and returns JSON-encoded responses. TaxCloud also supports Simple Object Access Protocol (SOAP) with identical API signatures.

## TaxCloud API Credentials — Is There a Developer Sandbox?
No. In our experience, so-called "developer sandbox" environments tend to behave differently than live production environments. Rather than operate a duplicate sandbox environment that could behave differently and require configuration changes between development and production use, all API calls to TaxCloud are received and processed in our live production environment.

Having said that, all API credentials (API ID + API KEY) are issued as test API credentials.

In TaxCloud, each "store" in your TaxCloud account is issued unique API credentials. You can have as many stores (and associated sets of API credentials) as you may need. Once you have completed your development and testing, you can return to the <a href="https://taxcloud.com/go/stores/" target="_blank">TaxCloud > Settings > Stores</a> area and set a single store to GO LIVE. Once a set of API credentials are LIVE, all transactions will be included in period sales tax reports and returns. Best practice would be to have at least two stores: one LIVE for your production retail or point-of-sale system, and one NOT LIVE for development and testing.

## Is Developer Support Available?
Our Customer Success Team can help if you are having issues with your API credentials or if you have questions about API responses, but they cannot write your software. Email support is available via service@taxcloud.net.