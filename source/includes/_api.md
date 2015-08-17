# API

You can use our REST API to access **nousrassemble** API endpoints, where you can find all data and proposals for a tenant, a user, ...

<aside class="warning">API is still in beta and you cannot create an App from the backend right now. Please write to <a href="mailto:dev@nousrassemble.com">dev@nousrassemble.com</a> to get an API token.</aside>


## Tenant

**nousrassemble** is a multi-tenancy plateform. To select a tenant for an endpoint, just use the tenant URL to query the API :
  
- Use <https://saint-quentin.nousrassemble.com> to reach endpoints for tenant *Saint Quentin*
- Use <https://grenoble.nousrassemble.com> to reach endpoints for tenant *Grenoble*

Some endpoint are global and cannot be reached with a tenant URL, so just use the global URL instead : <https://www.nousrassemble.com>

## Language

Some answers and actions can be localized, for example :

- error messages
- notifications
- global names for proposals
- ...

Set the user wanted language in the URL like this :

- <https://www.nousrassemble.com/fr/> for french for global endpoints
- <https://grenoble.nousrassemble.com/en/> for english on a specific tenant
