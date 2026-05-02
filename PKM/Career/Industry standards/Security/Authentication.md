# Authentication Methods
## 1. Password-Based Authentication
- Minimum 12 characters, complexity requirements
- Bcrypt, Argon2, or PBKDF2 for hashing (never MD5/SHA1)
- Salting to prevent rainbow table attacks

### 2. Multi-Factor Authentication (MFA)
Now considered the baseline for any serious system:
- TOTP (Time-based One-Time Password) — Google Authenticator, Authy (RFC 6238)
- FIDO2/WebAuthn — hardware keys (YubiKey), biometrics
- SMS OTP — common but weakest MFA option (SIM swapping risk)

### 3. Token-Based Authentication
For APIs and stateless systems:

- JWT (JSON Web Tokens) — self-contained, signed tokens (RS256 or ES256 preferred over HS256)
- OAuth 2.0 — delegated authorization framework (industry standard for third-party access)
- OpenID Connect (OIDC) — identity layer on top of OAuth 2.0


### 5. Passwordless Authentication
Growing standard, especially for consumer apps:
- Magic links (email-based)
- Passkeys (FIDO2) — replacing passwords entirely; adopted by Apple, Google, Microsoft
- Biometrics via device authenticators

### 6. SSO (Single Sign-On)
Enterprise standard:
- SAML 2.0 — dominant in enterprise/legacy systems
- OIDC — modern replacement, used by Google, Azure AD, Okta

### Key Security Principles Across All Methods
PrincipleWhat It MeansZero TrustNever trust, always verify — even internal trafficLeast PrivilegeTokens/sessions grant minimum necessary accessShort-lived tokensAccess tokens: 15 min; refresh tokens: days/weeksRevocationAlways support token/session invalidationRate limitingProtect login endpoints from brute forceAudit loggingLog all auth events for forensics
## 0Auth 2.0
- Authorization Server
- Scopes
- Openid Connect
- Access Token
- Refresh Token
- Resource Ower
- Client
- Redirect URL
- Grant Type
- Identity Provider