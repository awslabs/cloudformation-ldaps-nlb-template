## Configure an LDAPS Endpoint for Simple AD
CloudFormation Template that creates a NLB for TLS termination of LDAPS traffic versus Simple AD. Please review [the complete blog post](https://aws.amazon.com/blogs/security/how-to-configure-an-ldaps-endpoint-for-simple-ad/) for additional details about this solution.

### Solution Diagram
![](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2017/08/28/Screen-Shot-2017-07-25-at-10.30.54-AM.png)

Here is how the solution works, as shown in the preceding numbered diagram:
1. The LDAP client sends an LDAPS request to NLB on TCP port 636.
2. NLB terminates the SSL/TLS session and decrypts the traffic using a certificate. NLB sends the decrypted LDAP traffic to the Simple AD servers listening on TCP port 389.
3. The Simple AD servers send an LDAP response to NLB. NLB encrypts the response and sends it to the client.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

