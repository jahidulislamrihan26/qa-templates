# API Testing Checklist

## Contract
- [ ] There is a specification (OpenAPI). If not, write one from observed behaviour and the docs.
- [ ] Every success response matches its JSON Schema (types, required fields, formats), not only the status code.
- [ ] Content-Type is correct for every response, including errors.
- [ ] Every documented response code has a test that asserts exactly that code.

## Functional
- [ ] Create, read, update, delete each work, and data round-trips exactly (what you send is what you read back).
- [ ] Filters, sorting and paging return what they claim; boundaries (equal, one before, one after) are tested.
- [ ] Repeating a PUT or DELETE is safe (idempotent); a second DELETE gives 404.

## Validation (send bad data)
- [ ] Missing, null, wrong-type, empty, whitespace-only, too long, negative, decimal and unusual-format values give a 4xx with a useful message, never 500.
- [ ] The API never silently changes valid-looking data (truncating 99.99 to 99, reformatting dates).
- [ ] Wrong or missing Content-Type gives 415; unsupported Accept gives 406.
- [ ] Unknown fields are ignored or rejected, and never stored (no mass assignment).

## Authentication and authorisation
- [ ] No credentials, wrong credentials, expired and malformed tokens give 401 or 403, with no data in the body.
- [ ] A forbidden call changes nothing (read the resource afterwards).
- [ ] A user cannot read or change another user's resources (change the id).
- [ ] A failed login is not a 200.

## Security
- [ ] HTTPS only; plain HTTP redirects or is refused.
- [ ] Injection text in parameters, bodies and headers does not run or leak errors.
- [ ] Error responses leak no stack traces, file paths or framework names (`X-Powered-By`).
- [ ] Tokens, passwords and keys are not in URLs or logs.

## Robustness
- [ ] Odd ids (0, negative, fractional, huge, `1abc`, trailing slash, different case) behave consistently.
- [ ] HEAD, OPTIONS, ETag and conditional requests behave.
- [ ] Responses are fast enough (set a threshold and record p95, not only one call).

## Test data hygiene
- [ ] The suite creates its own data and deletes everything it created.
- [ ] No test depends on data other people can change.
- [ ] Reports are redacted before they are saved or published.
