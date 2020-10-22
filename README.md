# Async Airtable

[![Build: Linux](https://img.shields.io/github/workflow/status/GV14982/async-airtable/Linux?label=Build%3A%20Linux&logo=linux&logoColor=white&style=for-the-badge)](https://github.com/gv14982/async-airtable/actions)
[![Build: MacOS](https://img.shields.io/github/workflow/status/GV14982/async-airtable/Mac?label=Build%3A%20MacOS&logo=apple&logoColor=white&style=for-the-badge)](https://github.com/gv14982/async-airtable/actions)
[![Build: Windows](https://img.shields.io/github/workflow/status/GV14982/async-airtable/Windows?label=Build%3A%20Mac&logo=windows&logoColor=white&style=for-the-badge)](https://github.com/gv14982/async-airtable/actions)

[![Coverage](https://img.shields.io/coveralls/github/GV14982/async-airtable?style=for-the-badge)](https://coveralls.io/github/GV14982/async-airtable?branch=master)
[![MIT License](https://img.shields.io/github/license/GV14982/async-airtable?style=for-the-badge)](LICENSE.md)

AsyncAirtable is a lightweight npm package to handle working with the [Airtable API](https://airtable.com/api).

They have an existing library, but it is callback based and can get a little klunky at times, so I wrote this one that is promise based to make your life easier 😊.

## Requirements

- NodeJS
- npm
- [Airtable account](https://airtable.com/signup)

## Installation

- Be sure get your [API key](https://support.airtable.com/hc/en-us/articles/219046777-How-do-I-get-my-API-key-)

- To get the base ID of your new base. You can do this by heading over to [Airtable's API page](https://airtable.com/api) and selecting that base from the list, you should see:

  > The ID of this base is BASE_ID

- Install all dependancies:

```
npm install asyncairtable
```

Then you should be good to go!👍

## Usage

```javascript
const AsyncAirtable = require('async-airtable');
const asyncAirtable = new AsyncAirtable(API_KEY, BASE_ID);

asyncAirtable.select(TABLE_NAME, { ...OPTS }, PAGE_NUM);
asyncAirtable.find(TABLE_NAME, RECORD_ID);
asyncAirtable.createRecord(TABLE_NAME, { ...FIELDS });
asyncAirtable.updateRecord(TABLE_NAME, { RECORD_ID, ...FIELDS });
asyncAirtable.deleteRecord(TABLE_NAME, RECORD_ID);
asyncAirtable.bulkCreate(TABLE_NAME, [
  { ...FIELDS },
  { ...FIELDS },
  { ...FIELDS },
]);
asyncAirtable.bulkUpdate(TABLE_NAME, [
  { RECORD_ID, ...FIELDS },
  { RECORD_ID, ...FIELDS },
]);
asyncAirtable.bulkDelete(TABLE_NAME, [
  RECORD_ID,
  RECORD_ID,
  RECORD_ID,
  RECORD_ID,
]);
```

## License

[MIT](https://choosealicense.com/licenses/mit/)
