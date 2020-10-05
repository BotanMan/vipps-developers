# Technical newsletter for developers 2020-10

💥Draft!💥

This newsletter was sent in October 2020.

# Userinfo

Vipps now offers the possibility for merchants to
[ask for the user's profile information](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#userinfo)
as part of the payment flow. This is done by adding a scope
parameter to the initiate call: `POST:/ecomm/v2/payments`:

- address
- birthDate
- email
- name
- phoneNumber
- nin (fødselsnummer)
- accountNumbers

The Userinfo endpoint is shared with Vipps Login and the merchant needs to
have activated
[Vipps Login](https://github.com/vippsas/vipps-login-api)
to use this feature.

# PSP v3

Vipps is launching the
[PSP API v3](https://github.com/vippsas/vipps-psp-api)
to coincide with our migration of our users' cards from PAN to EMVco network
tokens. This technological migration is Vipps' strategy for achieving delegated
SCA once PSD2 comes into effect for card payments on January 1 2021.

The PSP API v3 is functionally identical to PSP API v2 apart from the
additional payment source format. There are also minor changes to naming of
properties to bring the API in line with Vipps' API standards.

Encrypted cards will still be sent for our users cards that have not yet been
migrated. Please see our [migration guide](v2-deprecation.md).

# Rate limiting

Vipps has implemented rate limiting on our external APIs in order to offer a
more robust and secure service. Most of these limits are only created to
counteract unexpected and erratic behaviour and it's nothing you should notice
under normal operation. More information about this is available in the
documentation for
[Vipps Recurring API](https://github.com/vippsas/vipps-recurring-api/blob/master/vipps-recurring-api.md#rate-limiting)
and
[Vipps eCom API](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#rate-limiting)

# Deprecations

## Deprecation of `/status`

The `/details` ending in the Vipps eCom API v2 offers more than the old
and long deprecated `/status` endpoint. We still see some customers using
the old endpoint and strongly recommend to update to the
[current one](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#get-payment-details).

## Deprecation of Vipps for Magento 1

The
[Vipps Payment Module for Magento 1](https://github.com/vippsas/vipps-magento-v1/blob/master/README.md)
is deprecated because of the high security risk in continued use of Magento 1.

# Reminders

We have mentioned some things before, and take this opportunity to remind you:

## API lifecycle

Our API lifecycle policy is
[available on GitHub](https://github.com/vippsas/vipps-developers/blob/master/vipps-api-lifecycle.md).

## Status pages for test and production environments

* Test: https://vipps-test.statuspage.io
* Production: https://vipps.statuspage.io

## How to get help quickly

Please see
[this page](https://github.com/vippsas/vipps-developers/blob/master/contact.md).

## Newsletter archive

Please see: https://github.com/vippsas/vipps-developers/tree/master/newsletters

# Questions or comments?

We're always happy to help with code or other questions you might have!
Please create [GitHub issues or pull requests](https://github.com/vippsas)
for the relevant API,
or [contact us](https://github.com/vippsas/vipps-developers/blob/master/contact.md).
