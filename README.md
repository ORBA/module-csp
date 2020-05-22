# Orba Csp

This module extends Magento_Csp in the following ways:
- allows to save CSV violation reports in a log file
- adds missing CSP rules

It improves the Magento CSP framework without impairing security.

### CSP Violation Reports

If configuration `Security > Orba CSP > General Configuration > Use built-in reporting` is enabled and no `report-uri` is specified in `csp_whitelist.xml`, CSP violation reports are sent to endpoint `/csp/report/` and saved in `/var/log/csp.log`.

Log file can be downloaded using a link in  `Stores > Configuration > Security > Orba CSP > General Configuration`.

### Additional CSP rules

The module whitelists additional resources such as `fonts.googleapis.com` and `www.google.com/recaptcha/`.

## Installation

```
composer require orba/module-csp
bin/magento module:enable Orba_Csp
bin/magento setup:upgrade
```

## Configuration

`Security > Orba CSP > General Configuration > Use built-in reporting` - if enabled and no `report-uri` is specified in `csp_whitelist.xml`, CSP violation reports are sent to endpoint `/csp/report/` and saved in a log file.
