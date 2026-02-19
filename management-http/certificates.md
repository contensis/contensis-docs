## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)

[Log in to add to favourites](/account/login)

Page last updated 07 April 2025

## Properties

Name

Type

Format

Description

Example

**id**

string

GUID

The unique identifier of the certificate as a 128 bit GUID

**Status**

string

\-

Indicates the current status of the certificate. Can be either disabled or enabled.

**commonName**

string

\-

The common name (CN) for the certificate, which is typically the domain name the certificate is issued for.

www.mysite.com

**keySize**

integer

\-

The size of the cryptographic key in bits.

4096

**issuer**

string

\-

The organization that issued the certificate, typically a Certificate Authority

DigiCert

**public**

string

\-

The public certificate in PEM format. This contains the public key and other metadata about the certificate

**issued**

datetime

datetime

The date and time when the certificate was issued.

**sans**

string\[...\]

\-

A list of Subject Alternative Names (SANs). These are additional domain names that the certificate covers.

**expiry**

datetime

datetime

The date and time when the certificate will expire and no longer be valid.

**version**

object

[version](/help-and-docs/apis/management-http/content/version)

Version info specific to the certificate

## Example

JSON

```
		{
			"id": "2f349e99-615f-4575-b740-7cad4bb61b5c",
			"status": "enabled",
			"commonName": "www.fictitious.com",
			"keySize": 4096,
			"issuer": "Fictitious Ltd",
			"public": "-----BEGIN CERTIFICATE-----\nMIIF/TCCA+WgAwIBAgIULjEg//d4Ivi/g7Jk22R9CvuEm+IwDQYJKoZIhvcNAQEL\nBQAwgY0xCzAJBgNVBAYTAlVLMRMwEQYDVQQIDApTaHJvcHNoaXJlMQ8wDQYDVQQH\nDAZMdWRsb3cxFzAVBgNVBAoMDkZpY3RpdGlvdXMgTHRkMRswGQYDVQQDDBJ3d3cu\nZmljdGl0aW91cy5jb20xIjAgBgkqhkiG9w0BCQEWE2luZm9AZmljdGl0aW91cy5j\nb20wHhcNMjMxMjE4MTE0MjA1WhcNMzMxMjE1MTE0MjA1WjCBjTELMAkGA1UEBhMC\nVUsxEzARBgNVBAgMClNocm9wc2hpcmUxDzANBgNVBAcMBkx1ZGxvdzEXMBUGA1UE\nCgwORmljdGl0aW91cyBMdGQxGzAZBgNVBAMMEnd3dy5maWN0aXRpb3VzLmNvbTEi\nMCAGCSqGSIb3DQEJARYTaW5mb0BmaWN0aXRpb3VzLmNvbTCCAiIwDQYJKoZIhvcN\nAQEBBQADggIPADCCAgoCggIBAN/VWmzMN7hILCSnW+zLVEB+F1gwrPBEp9+McbeY\n9+vUB/YFCt74OY+/moK/4vwTzcAvGCcIJS6pnGoaB95JeiAmR+ZardLxE7k9RDZa\n/kbNXTiGsabCDvda+Lfu/MOPOsBqb1qGmfEtY+vUoBXwhAWk6dGw3n4Ha6583dUU\nZJ4JsDL/iZUeLdhMaqQymZ1CUqf/d4XpkKPj00M32iThhsOyd1Pz3OFpF/9/MWV/\nvLAk7zn+6HjG4kzPyXUKJj4JXG7/kSyd2Y9+7KYlNoyXtRvjQcMle34bpaC+e9xW\nFXKijIU9lduUh5Zjs8+ejT58rq9JQ1yTHloFQ9H0EtjEcRMwo/1iK9gNlbdGnWXw\nAYsu/84yjcmZDMkXoel6ZrLwXvokgWwVutTvXeLF10G8ce2iUMy9L1C3jA9yAVfD\nn3f3V9KG6ouncVoUzsQbTz/v7VkVKtAusI93MuetYVwRLghfbq3ALeAO9W+p9me5\na6Guc1Q88blaLP4q3r+FEQdMmuyhq/Lo6fAibOC798RzU6/cd9WYBZIgTTf9H6+j\nPH7AJwEZuVdicKjAk5p2L5kFYglAzcMIFrNYLSTKYk9fD5HlCwBJwpYASEe6Dnp3\nXuQ1V8Bjr2S3NgmIS7tpeRgyU7gi1sGRXzCQ1McnLG1SpEVi3HTgGhMSkpLx4Y7T\nCId5AgMBAAGjUzBRMB0GA1UdDgQWBBSvC4g1mtta34ruaxiFlRCOZ5gGhDAfBgNV\nHSMEGDAWgBSvC4g1mtta34ruaxiFlRCOZ5gGhDAPBgNVHRMBAf8EBTADAQH/MA0G\nCSqGSIb3DQEBCwUAA4ICAQA/x/BERkI6MARn/aSQ9Z2zM6dAaNyR7lC/nWT4EkPQ\nTQ6WMD4w2vARdiAeycSTH9O2nLPg0CX1u47dXUDtPnAPRguOmKdjvcWmX5GqJBdU\nJhgdBwlDAnmqxo5bJiSWOGaQDr7oTZt0oq4ebJ25KXemWYcT01gwwwhqYsTx8Bf2\nDyMXHRjLbHfUP8vTIf3BPgz+IdKi2R2pRInwvvK0FOkpAwbkc5x2gEWq3GZjTNIw\nZjRtYm5HB7fG2/FODNyAOWpuHNJvyuDCx2rZKt5HXik9buh3kZuBJWerMaHnB28F\nBTh3HD2AQ05hyaGBhqkBwI9+0q5Ch/8SGds4cZpBRQ3VnHMeXyAz0Eo5rpbduXJ7\nYxZ0E01860espo54jNGwgzn0jcGiYbP3rTLha6klso1Q2Mo/6m7ERm95hoyjFF9b\nxohQimMYGoxlr/wX2V9H9kQbNa+wWXAHMb7e5XTribEEnSAGDJeV+mTqyuD26yJN\nuBnSw+tGSa5k8PIXJgYOv6X+2R+9H2NJrYIgynpEKf9i9WBLNG7xzFTaSSW/KhDD\nImi/700EUDINcYR+R6DrKizXGVG0O+WbbsZvrS4Fu8DrGv5UOOoh8co4QDMIS8cV\nF8af+xqATk09j610P+51baHqC023EJzp0LKJ/dvDFkuasq4FZLXHsHGJj4NmMUoi\nuw==\n-----END CERTIFICATE-----",
			"issued": "2023-12-18T11:42:05",
			"sans": [],
			"expiry": "2033-12-15T11:42:05",
			"version": {
				"created": "2023-12-18T11:44:28.611687",
				"createdBy": "7685e4c9-9b1d-4336-96f8-69b329403019"
			}
		}
```