# OAuth2-authorizedGrantTypes-
In Spring Security OAuth2, the authorizedGrantTypes attribute specifies the grant types that are allowed for a client when requesting access tokens. The available options for the authorizedGrantTypes attribute are:

authorization_code: This grant type is used for web-based applications where the client redirects the user to the authorization server for authentication, and then the authorization server redirects back to the client with an authorization code.

password: This grant type is used when the client collects the user's username and password and sends them directly to the authorization server to obtain an access token. This is typically used for trusted clients and is not recommended for public clients.

implicit: This grant type is used for single-page applications or mobile apps where the client requests an access token directly from the authorization server without going through a server-side component.

client_credentials: This grant type is used when the client itself is the resource owner, and it requests an access token from the authorization server based on its own credentials (client ID and client secret).

refresh_token: This grant type is used to obtain a new access token using a refresh token that was previously issued. It allows clients to maintain access without requiring the user to re-authenticate.

urn:ietf:params:oauth:grant-type:jwt-bearer: This grant type is used when the client presents a JWT (JSON Web Token) as a credential to obtain an access token.

Custom grant types: You can define custom grant types if needed for specific authentication and authorization scenarios.

The choice of grant type depends on the specific requirements and security considerations of your application. Each grant type has its own use cases and security implications, so it's important to choose the one that best fits your application's needs.

<strong>The ClientBuilder class appears to be a builder pattern implementation for constructing instances of ClientDetails used in OAuth 2.0 client configurations. It provides a fluent interface to set various properties and attributes of an OAuth 2.0 client. Below is a list of fields and methods in the ClientBuilder class, along with explanations:

Fields:

private final String clientId: A required field representing the unique identifier for the OAuth 2.0 client being constructed.

private Collection<String> authorizedGrantTypes: A collection to specify the authorized grant types for the client. Grant types define how the client can obtain an access token.

private Collection<String> authorities: A collection of authorities associated with the client. These authorities determine the client's permissions.

private Integer accessTokenValiditySeconds: The validity period of the access token in seconds.

private Integer refreshTokenValiditySeconds: The validity period of the refresh token in seconds.

private Collection<String> scopes: A collection of scopes associated with the client. Scopes define the level of access the client has.

private Collection<String> autoApproveScopes: A collection of scopes that are automatically approved without user consent if the autoApprove flag is set.

private String secret: The client's secret, used for authentication.

private Set<String> registeredRedirectUris: A set of URIs to which the authorization server can redirect the user after authentication and authorization.

private Set<String> resourceIds: A set of resource identifiers associated with the client.

private boolean autoApprove: A flag indicating whether the client scopes are auto-approved without user consent.

private Map<String, Object> additionalInformation: Additional information associated with the client.

Methods:

private ClientDetails build(): Builds and returns an instance of ClientDetails with the specified configuration.

public ClientBuilder resourceIds(String... resourceIds): Sets the resource IDs associated with the client.

public ClientBuilder redirectUris(String... registeredRedirectUris): Sets the registered redirect URIs for the client.

public ClientBuilder authorizedGrantTypes(String... authorizedGrantTypes): Sets the authorized grant types for the client.

public ClientBuilder accessTokenValiditySeconds(int accessTokenValiditySeconds): Sets the access token validity period in seconds.

public ClientBuilder refreshTokenValiditySeconds(int refreshTokenValiditySeconds): Sets the refresh token validity period in seconds.

public ClientBuilder secret(String secret): Sets the client's secret.

public ClientBuilder scopes(String... scopes): Sets the scopes associated with the client.

public ClientBuilder authorities(String... authorities): Sets the authorities (permissions) associated with the client.

public ClientBuilder autoApprove(boolean autoApprove): Sets whether the client scopes are auto-approved without user consent.

public ClientBuilder autoApprove(String... scopes): Sets specific scopes to be auto-approved.

public ClientBuilder additionalInformation(Map<String, ?> map): Sets additional information associated with the client using a map.

public ClientBuilder additionalInformation(String... pairs): Sets additional information using key-value pairs (e.g., "key:value").

public ClientDetailsServiceBuilder<B> and(): Returns the parent builder (ClientDetailsServiceBuilder) to continue configuring clients.

private ClientBuilder(String clientId): Private constructor that initializes the clientId.

This builder pattern simplifies the creation of client configurations for OAuth 2.0 clients by allowing developers to set various attributes in a chainable and expressive manner.   </strong>


