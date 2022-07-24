# Week 3

## XSS

- [XSS payloads](https://github.com/payloadbox/xss-payload-list)
- [XSS payloads 2](https://github.com/pgaijin66/XSS-Payloads/blob/master/payload/payload.txt)
- [XSSer](https://github.com/epsylon/xsser)

## Broken Access Control

How to get there ?

- Dev Tools > Storage > Session Storage
  - bid (buyer id)
  - uses a key value store and by changing stuff in the store, you are able to access different values

## XXE

Using xml files to do malicious shit

- [payloads](https://github.com/payloadbox/xxe-injection-payload-list)

## SQL Injection

- [SQL Refresher](https://www.w3schools.com/sql/)

what a login screen looks like When a user enters their email as `test`
SQL:

```sql
SELECT * FROM Users WHERE email='test'
```

to be malicious the user can enter `test' OR 1 = 1; --`
SQL:

```sql
SELECT * FROM Users WHERE email='tes' OR 1 = 1; --'
```

This should show the first user

## Burpsuite

loggining into admin in a differnt way. (Intruder tab)

Proxy Intercept > Sent to Intruder > Intruder > Postitions > Select Password > add > sniper > Payloads > Payload options > start attack

**Finding the correct login**

- Sort by Status code
- Sort by Length
- grep on certain words in the response
