# in.tblO365Domains

​​​​Domain names defined in an Office 365 subscription. Corresponds to the Domains tab in the Office 365 administration portal.​

| Name               | Data Type     | Mandatory | Key                               | Comment                                                                                                                                                                                                                                                                                                                                                            |
|--------------------|---------------|-----------|-----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DataSourceId       | varcha​r(32)   | Y         |                                   | Unique ID of the source of this record.                                                                                                                                                                                                                                                                                                                            |
| DomainId           | nvarchar(256) | Y         | Primary Key                       | The fully qualified name of the domain.                                                                                                                                                                                                                                                                                                                            |
| TenantId           | nvarchar(128) | Y         | FK > tblO365Organization​.TenantId​ | The unique identifier for the tenant.                                                                                                                                                                                                                                                                                                                              |
| AuthenticationType | varchar(32)   |           |                                   | Indicates the configured authentication type for the domain. The value is either Managed or Federated. Managed indicates a cloud managed domain where Azure AD performs user authentication. Federated indicates authentication is federated with an identity provider such as the tenant's on-premises Active Directory via Active Directory Federation Services. |
| IsAdminManaged     | bit           |           |                                   | The value of the property is false if the DNS record management of the domain has been delegated to Office 365. Otherwise, the value is true.                                                                                                                                                                                                                      |
| IsDefault          | bit           |           |                                   | True if this is the default domain that is used for user creation. There is only one default domain per company.                                                                                                                                                                                                                                                   |
| IsInitial          | bit           |           |                                   | True if this is the initial domain created by Microsoft Online Services (companyname&#46;onmicrosoft&#46;com). There is only one initial domain per company.                                                                                                                                                                                                               |
| IsRoot             | bit           |           |                                   | True if the domain is a verified root domain. Otherwise, false if the domain is a subdomain or unverified.                                                                                                                                                                                                                                                         |
| SupportedServices  | nvarchar(512) |           |                                   | The capabilities assigned to the domain. Semi-colon separated string of 0, 1 or more of following values: Email, Sharepoint, EmailInternalRelayOnly, OfficeCommunicationsOnline, SharePointDefaultDomain, FullRedelegation, SharePointPublic, OrgIdAuthentication, Yammer, Intune                                                                                  |