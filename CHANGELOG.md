# Changes

## 0.9.0

* [Rust 2018 Refactor](https://github.com/tiny-http/tiny-http/pull/208)
* [Enable prompt responses, before the request has been fully read](https://github.com/tiny-http/tiny-http/pull/207)

  This isn't an API change, but does result in different behaviour to 0.8.2 and so justifies a minor version bump.

  HTTP requests now return a boxed `FusedReader` which drops the underlying
  reader once it reaches EOF, such that the reader no longer needs to be
  explicitly consumed and the server may now respond with e.g. a "413 Payload
  too large" without waiting for the whole reader.

* Bumped the minimum compiler version tested by CI to 1.48 (the version supported in Debian Bullseye)

## 0.8.2

* [Add TestRequest for writing server tests more easily](https://github.com/tiny-http/tiny-http/pull/203)

## 0.8.1

* [Don't set Transfer-Encoding for 1xx or 204 Responses](https://github.com/tiny-http/tiny-http/pull/198)

## 0.8.0

* [Fix RUSTSEC-2020-0031](https://github.com/tiny-http/tiny-http/pull/190)
* [Filter out the same socket-closing errors on flush as on write](https://github.com/tiny-http/tiny-http/pull/192)
* [response: Drop the use of EqualReader for TransferEncoding::Identity](https://github.com/tiny-http/tiny-http/pull/183)
* [Add unblock method for graceful shutdown](https://github.com/tiny-http/tiny-http/pull/184)
* [Response: Don't forget `chunked_threshold`](https://github.com/tiny-http/tiny-http/pull/177)
* [Response: Allow manual handling of Range requests](https://github.com/tiny-http/tiny-http/pull/175)
* [Feature | Getters for Response Status Code & Data Length Properties](https://github.com/tiny-http/tiny-http/pull/186)

## 0.7.0

* [Fix HTTPS deadlock](https://github.com/tiny-http/tiny-http/pull/151)
* [Relicense to MIT/Apache-2.0](https://github.com/tiny-http/tiny-http/pull/163)
* [Update `ascii` dependency](https://github.com/tiny-http/tiny-http/pull/165)
* [Fix typo in README](https://github.com/tiny-http/tiny-http/pull/171)
* [Fix compilation errors in benchmark](https://github.com/tiny-http/tiny-http/pull/170)
* [Update `url` dependency](https://github.com/tiny-http/tiny-http/pull/168)
* [Update `chunked_transfer` dependency](https://github.com/tiny-http/tiny-http/pull/166)

## 0.6.2

* [Remove AsciiExt usage](https://github.com/tiny-http/tiny-http/pull/152)
* [Remove unused EncodingDecoder](https://github.com/tiny-http/tiny-http/pull/153)

## 0.6.1

* [Fix documentation typo](https://github.com/tiny-http/tiny-http/pull/148)
* [Expose chunked_threshold on Response](https://github.com/tiny-http/tiny-http/pull/150)

## 0.6.0

* [Bump dependencies](https://github.com/tiny-http/tiny-http/pull/142)
* [Fix `next_header_source` alignment](https://github.com/tiny-http/tiny-http/pull/140)

## 0.5.9

* Expanded and changed status code description mapping according to IANA registry:
 * https://github.com/tiny-http/tiny-http/pull/138

## 0.5.8

* Update links to reflect repository ownership change: https://github.com/frewsxcv/tiny-http -> https://github.com/tiny-http/tiny-http

## 0.5.7

* Fix using Transfer-Encoding: identity with no content length
 * https://github.com/tiny-http/tiny-http/pull/126

## 0.5.6

* Update link to documentation
 * https://github.com/tiny-http/tiny-http/pull/123
* Fix websockets
 * https://github.com/tiny-http/tiny-http/pull/124
* Drop the request reader earlier
 * https://github.com/tiny-http/tiny-http/pull/125

## 0.5.5

* Start using the log crate
 * https://github.com/tiny-http/tiny-http/pull/121
* Unblock the accept thread on shutdown
 * https://github.com/tiny-http/tiny-http/pull/120

## 0.5.4

* Fix compilation warnings
 * https://github.com/tiny-http/tiny-http/pull/118

## 0.5.3

* Add try_recv_timeout function to the server
 * https://github.com/tiny-http/tiny-http/pull/116

## 0.5.2

* Update ascii to version 0.7
 * https://github.com/tiny-http/tiny-http/pull/114

## 0.5.1

* Request::respond now returns an IoResult
 * https://github.com/tiny-http/tiny-http/pull/110

## 0.5.0

* HTTPS support
 * https://github.com/tiny-http/tiny-http/pull/107
* Rework the server creation API
 * https://github.com/tiny-http/tiny-http/pull/106

## 0.4.1

* Allow binding to a nic by specifying the socket address
 * https://github.com/tiny-http/tiny-http/pull/103

## 0.4.0

* Make Method into an enum instead of a character string
 * https://github.com/tiny-http/tiny-http/pull/102
