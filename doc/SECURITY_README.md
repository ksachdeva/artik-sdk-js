# SECURITY API

## get_certificate

```javascript
String get_certificate(String cert_id)
```

**Description**

Return the certificate stored in the Secure Element in PEM format

**Parameters**

*String*: Certificate identifier. Must be **artik** or **manufacturer**

**Return value**

*String*: PEM certificate or error information

**Example**

```javascript
console.log(get_certificate('artik'))
```

## get_ca_chain

```javascript
String get_ca_chain(String cert_id)
```

**Description**

Return the Certificate Authority chain of the device in PEM format.
It contains one or more certificates used for verifying the device
certificate stored in the SE.

**Parameters**

*String*: Certificate identifier. Must be **artik** or **manufacturer**

**Return value**

*String*: PEM certificate(s) or error information

**Example**

```javascript
console.log(get_ca_chain('artik'))
```

## get_key_from_cert

```javascript
String get_key_from_cert(String certificate)
```

**Description**

Return the private key matching the certificate passed
as a parameter. The return string is in PEM format.

**Parameters**

*String*: PEM certificate from which to extract the private key.

**Return value**

*String*: PEM private key or error information

**Example**

```javascript
var cert = get_certificate('artik')
console.log(get_key_from_cert(cert))
```

## get_certificate_sn

```javascript
Buffer get_certificate_sn(String cert_id)
```

**Description**

Return the serial number extracted from the device certificate
stored in the Secure Element. It is returned as a buffer of bytes.

**Parameters**

*String*: Certificate identifier. Must be **artik** or **manufacturer**

**Return value**

*Buffer*: serial number

**Example**

```javascript
console.log(get_certificate_sn('artik'))
```

## get_random_bytes

```javascript
Buffer get_random_bytes(Number length)
```

**Description**

Return a buffer of N bytes generated by the Secure Element.

**Parameters**

*Number*: length in bytes of the random buffer to generate.

**Return value**

*Buffer*: generated random bytes.

**Example**

```javascript
console.log(get_random_bytes(64))
```

