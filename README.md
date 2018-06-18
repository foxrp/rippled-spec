rippled-spec
============

The `rippled` API specification defined in `JSON`.

These files can be used by developers to programmatically generate or validate transactions and API method calls.

## API

API specification can be loaded from [`api.json`](spec/transactions.json).

## Transactions

The transaction spec defines transaction types and their field detail.

The transaction specification can be loaded from [`transactions.json`](spec/transactions.json).

## Transaction Type Validation

Validation can occur at the transaction type level, or the field level.

A `validation` property will occur at either level when appropriate.

### Field Level Validations

Validations for field types like `Unsigned Integer` are not explicitly defined.

- min: Minimum value allowed.
- max: Maximum value allowed.
- allow_zero: Sometimes allowed values will be a range above zero, however zero is also allowed.
- regex: Regular expression for string formats.


### Transaction Type Level Validations

There are cases where a field is required or not allowed based on another one being defined. This is where group
validation comes into play.

Group types:
- `exclusive`: Only one of the fields is allowed. If `required` is set, then at least one of them is required.
- `dependent`: If one of the fields in the group is defined, then the rest are required.