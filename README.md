[![NPM Version](https://badge.fury.io/js/js-rules-engine.svg)](https://badge.fury.io/js/driver-license-validator)
[![Build Status](https://travis-ci.org/justinlettau/driver-license-validator.svg?branch=master)](https://travis-ci.org/justinlettau/driver-license-validator)
[![Dev Dependency Status](https://david-dm.org/justinlettau/driver-license-validator/dev-status.svg)](https://david-dm.org/justinlettau/js-rules-engine?type=dev)
[![codecov](https://codecov.io/gh/justinlettau/driver-license-validator/branch/master/graph/badge.svg)](https://codecov.io/gh/justinlettau/driver-license-validator)

# Driver License Validator
Validate driver license numbers.
Formats based on [https://ntsi.com/drivers-license-format/](https://ntsi.com/drivers-license-format/).

# Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Development](#development)

# Installation
```bash
npm install driver-license-validator --save
```

# Usage
```js
import { validate } from 'driver-license-validator';

validate('A1234567');
// => [
//   { description: '1 letter followed by 1-8 numbers', state: 'AZ' },
//   { description: '1 letter followed by 7 numbers', state: 'CA' },
//   { description: '1 letter followed by 5-9 numbers', state: 'MO' },
//   { description: '1 letter followed by 6-8 numbers', state: 'NE' },
//   { description: '1 letter followed by 7 numbers', state: 'NY' },
//   { description: '1 letter followed by 4-8 numbers', state: 'OH' }
// ]

validate('A1234567', 'NY');
// => [
//   { description: '1 letter followed by 7 numbers', state: 'NY' }
// ]

validate('A1234567', ['NY', 'OH']);
// => [
//   { description: '1 letter followed by 7 numbers', state: 'NY' },
//   { description: '1 letter followed by 4-8 numbers', state: 'OH' }
// ]

validate('invalid_dl');
// => null
```

# Development
```
npm install
npm run build
```
