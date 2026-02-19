1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Certificates](https://www.contensis.com/help-and-docs/apis/management-http/certificates)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 26 June 2024

POST/api/management/certificates/

## Parameters

Name

Parameter type

Type

Description

**private***(required)*

body

string

This property contains the private key of the certificate in PEM format. The PEM format is a base64 encoded ASCII string enclosed between "-----BEGIN PRIVATE KEY-----" and "-----END PRIVATE KEY-----" markers.

**public***(required)*

body

string

This property contains the public certificate in PEM format. The public certificate includes the public key and additional information about the entity it represents (such as the domain name, the issuing Certificate Authority, and validity dates). The PEM format here is also a base64 encoded ASCII string enclosed between "-----BEGIN CERTIFICATE-----" and "-----END CERTIFICATE-----" markers.

**chain**

body

string\[...\]

This property contains an array of intermediate certificates (if any) in PEM format. Intermediate certificates form the chain of trust between the end-entity certificate (the public certificate) and the root certificate from a trusted Certificate Authority (CA)

## Responses

HTTP status code

Reason

Model

**200**

Success

[Certificate](https://www.contensis.com/help-and-docs/apis/management-http/certificates)

**401**

Unauthorized

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**403**

Forbidden

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**404**

Project not found

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**409**

Resource already exists

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**422**

Validation error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

**500**

Internal server error

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

## Examples

JSON

```
POST

{
	"private": "-----BEGIN PRIVATE KEY-----...-----END PRIVATE KEY-----",
	"public": "-----BEGIN CERTIFICATE-----\nMIIF/TCCA+WgAwIBAgIULjEg//d4Ivi/g7Jk22R9CvuEm+IwDQYJKoZIhvcNAQEL\nBQAwgY0xCzAJBgNVBAYTAlVLMRMwEQYDVQQIDApTaHJvcHNoaXJlMQ8wDQYDVQQH\nDAZMdWRsb3cxFzAVBgNVBAoMDkZpY3RpdGlvdXMgTHRkMRswGQYDVQQDDBJ3d3cu\nZmljdGl0aW91cy5jb20xIjAgBgkqhkiG9w0BCQEWE2luZm9AZmljdGl0aW91cy5j\nb20wHhcNMjMxMjE4MTE0MjA1WhcNMzMxMjE1MTE0MjA1WjCBjTELMAkGA1UEBhMC\nVUsxEzARBgNVBAgMClNocm9wc2hpcmUxDzANBgNVBAcMBkx1ZGxvdzEXMBUGA1UE\nCgwORmljdGl0aW91cyBMdGQxGzAZBgNVBAMMEnd3dy5maWN0aXRpb3VzLmNvbTEi\nMCAGCSqGSIb3DQEJARYTaW5mb0BmaWN0aXRpb3VzLmNvbTCCAiIwDQYJKoZIhvcN\nAQEBBQADggIPADCCAgoCggIBAN/VWmzMN7hILCSnW+zLVEB+F1gwrPBEp9+McbeY\n9+vUB/YFCt74OY+/moK/4vwTzcAvGCcIJS6pnGoaB95JeiAmR+ZardLxE7k9RDZa\n/kbNXTiGsabCDvda+Lfu/MOPOsBqb1qGmfEtY+vUoBXwhAWk6dGw3n4Ha6583dUU\nZJ4JsDL/iZUeLdhMaqQymZ1CUqf/d4XpkKPj00M32iThhsOyd1Pz3OFpF/9/MWV/\nvLAk7zn+6HjG4kzPyXUKJj4JXG7/kSyd2Y9+7KYlNoyXtRvjQcMle34bpaC+e9xW\nFXKijIU9lduUh5Zjs8+ejT58rq9JQ1yTHloFQ9H0EtjEcRMwo/1iK9gNlbdGnWXw\nAYsu/84yjcmZDMkXoel6ZrLwXvokgWwVutTvXeLF10G8ce2iUMy9L1C3jA9yAVfD\nn3f3V9KG6ouncVoUzsQbTz/v7VkVKtAusI93MuetYVwRLghfbq3ALeAO9W+p9me5\na6Guc1Q88blaLP4q3r+FEQdMmuyhq/Lo6fAibOC798RzU6/cd9WYBZIgTTf9H6+j\nPH7AJwEZuVdicKjAk5p2L5kFYglAzcMIFrNYLSTKYk9fD5HlCwBJwpYASEe6Dnp3\nXuQ1V8Bjr2S3NgmIS7tpeRgyU7gi1sGRXzCQ1McnLG1SpEVi3HTgGhMSkpLx4Y7T\nCId5AgMBAAGjUzBRMB0GA1UdDgQWBBSvC4g1mtta34ruaxiFlRCOZ5gGhDAfBgNV\nHSMEGDAWgBSvC4g1mtta34ruaxiFlRCOZ5gGhDAPBgNVHRMBAf8EBTADAQH/MA0G\nCSqGSIb3DQEBCwUAA4ICAQA/x/BERkI6MARn/aSQ9Z2zM6dAaNyR7lC/nWT4EkPQ\nTQ6WMD4w2vARdiAeycSTH9O2nLPg0CX1u47dXUDtPnAPRguOmKdjvcWmX5GqJBdU\nJhgdBwlDAnmqxo5bJiSWOGaQDr7oTZt0oq4ebJ25KXemWYcT01gwwwhqYsTx8Bf2\nDyMXHRjLbHfUP8vTIf3BPgz+IdKi2R2pRInwvvK0FOkpAwbkc5x2gEWq3GZjTNIw\nZjRtYm5HB7fG2/FODNyAOWpuHNJvyuDCx2rZKt5HXik9buh3kZuBJWerMaHnB28F\nBTh3HD2AQ05hyaGBhqkBwI9+0q5Ch/8SGds4cZpBRQ3VnHMeXyAz0Eo5rpbduXJ7\nYxZ0E01860espo54jNGwgzn0jcGiYbP3rTLha6klso1Q2Mo/6m7ERm95hoyjFF9b\nxohQimMYGoxlr/wX2V9H9kQbNa+wWXAHMb7e5XTribEEnSAGDJeV+mTqyuD26yJN\nuBnSw+tGSa5k8PIXJgYOv6X+2R+9H2NJrYIgynpEKf9i9WBLNG7xzFTaSSW/KhDD\nImi/700EUDINcYR+R6DrKizXGVG0O+WbbsZvrS4Fu8DrGv5UOOoh8co4QDMIS8cV\nF8af+xqATk09j610P+51baHqC023EJzp0LKJ/dvDFkuasq4FZLXHsHGJj4NmMUoi\nuw==\n-----END CERTIFICATE-----",
	"chain": []
}
```