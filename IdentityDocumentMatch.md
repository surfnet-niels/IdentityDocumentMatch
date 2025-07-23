# REFEDS Assurance Framework version 2.0 Addendum - IdentityDocumentMatch

Version History: V0.1

Status: Draft

Date: 2025-06-27

Editor: Niels van Dijk (SURF)

# 1. Purpose and Scope

This section is informative

The REFEDS Assurance Framework version 2.0 \[RAF2.0\] provides a
framework by which a Credential Service Provider (CSP) asserts claims to
a Relying Party's (RP\'s) service about its confidence in the values of
selected user attributes.

This document addends RAF 2.0 by providing an additional claim a CSP may
issue towards a RP: Identity Document Match.

Identity Document Match allows a CSP to express how the name and date of
birth attribute values provided to the RP relate to the information
presented to the CSP at the time of identity validation.

# 2. Terms and Definitions

No changes

# 3. Conformance Criteria

No changes

# 4. Versioning

No changes

# 5. Assurance Components

## 5.1 Identity Document Match

This section is normative.

Identity Document Match allows a CSP to express how of the attribute
values provided to the RP relate to the information presented to the CSP
at the time of identity (re)validation.

The requirements are limited to name and date of birth attributes. For
name attributes when using SAML either 'givenName' and 'sn (surname)' or
'cn (commonName)' \[eduPerson\], when using claims either 'given_name'
and 'familiy_name' and optionally 'middle_name' or 'name' \[OIDC-core\].
For date of birth when using SAML 'schacDateOfBirth' \[SCHAC\], when
using claims birthdate \[OIDC-core\]

By asserting Identity Document Match name related claims, the CSP states
the values presented in one or more of the name attributes are *an exact
literal match* as compared to the values found on the Identity
Evidence.
By asserting an Identity Document Match date of birth claim, the CSP
states the values for year, month and day are *equivalent to the values*
as found on the Identity Evidence. To support localization, the date
format is out of scope for the matching, hence for example '24-12-2025'
(dd-mm-yyyy), '12/24/2025' (mm/dd/yyyy), '24 december 2025' and 'dec 24,
2025' are all considered to be equivalent.

The CSP MUST perform the comparison at the time of the identity proofing
process. For a CSP to assert Identity Document Match claims, the
identity proofing process MUST be equivalent to IAP values "medium" or
"high" as described in RAF chapter 5.2.1, and either
https://refeds.org/assurance/IAP/medium or
https://refeds.org/assurance/IAP/high MUST be present in the assurance
attributes.
If any of the attributes mentioned in this section are changed, for
example because of changes in the persons name, the CSP MUST perform
comparison of the Identity Evidence within 31 calender days.

To assert Identity Document Match claims in accordance with this
specification, the CSP MUST use below <https://refeds.org/assurance/IDM>
values. If so applicable, one or more values MAY be used in combination.

| Value                                     | Description                      |
|-------------------------------------------|----------------------------------|
| https://refeds.org/assurance/IDM/name-1   | The values presented in the assertion of ‘givenName’ and ‘sn (surname)’ [eduPerson] or ‘given_name’  and ‘familiy_name’ and optionally ‘middle_name’ [OIDC-core] are identical to the values found in the  Identity Evidence which was used to identity proof the user |
| https://refeds.org/assurance/IDM/name-2   | The values presented in the assertion of ‘cn (commonName)’ [eduPerson] or ‘name’ [OIDC-core] are identical to the values found in the  Identity Evidence which was used to identity proof the user |
| https://refeds.org/assurance/IDM/dob | The values presented in the assertion of ‘schacDateOfBirth’ [SCHAC] or ‘birthdate’ [OIDC-core] are equivalent to the values found in the Identity Evidence which was used to identity proof the user |

Please note that by asserting Identity Document Match claims, the CSP
*does not* assert any guarantee any of the names constitutes the persons
'legal name' \[wp-legal-name\], nor in any way makes statements on how
the name attributes are constructed. Identity Document Match claims
simply reflects the result of the comparison performed by the CSP.

# 6. Assurance Profiles

No changes

# 7. Representation on Federated Protocols

No changes

# 8. References

\[RAF2.0\]\
<https://refeds.org/wp-content/uploads/2023/12/RAF-2.0-Final-version.pdf>

\[SCHAC\]
<https://wiki.refeds.org/display/STAN/SCHAC+Releases?preview=/44957731/128909315/SCHAC%2B1.6.0-final.pdf>

\[OIDC-core\]\
<https://openid.net/specs/openid-connect-core-1_0.html#StandardClaims>

\[wp-legal-name\]

<https://en.wikipedia.org/wiki/Legal_name>

# 9. Acknowledgements

The editor of this document would like to thank the following for
contributing:

-   Albert Wu - Incommon/Internet2
-   Alan Buxey - MyUnidays
-   Fredrik Domeij - SWAMID
-   Guy Halse - SAFIRE/Tenet
-   Jan Oppolzer - Cesnet
-   John Scullen - AAF
-   Jon Agland - UK federation (Jisc)
-   Matthew Slowe - (UKf/Jisc)
-   Nicole Harris - GEANT
-   Pål Axelsson - SUnet
-   Pete Birkinshaw - Digital Identity Ltd
-   Scott Cantor - Ohio State University
-   Shannon Roddy
-   Tom Barton - Internet2
