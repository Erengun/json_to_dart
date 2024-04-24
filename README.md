# JSON to Dart

This is a fork of [json_to_dart](https://github.com/javiercbk/json_to_dart) by [Javier Lecuona](https://github.com/javiercbk) with some modifications to make it work with the latest Dart SDK.

I aim to maintain this fork and keep it up to date with the latest Dart SDK. 

Warning: This is a work in progress and may not work as expected.

Given a JSON string, this library will generate all the necessary Dart classes to parse and generate JSON.

This library is designed to generate Flutter friendly model classes following the [flutter's doc recommendation](https://flutter.io/json/#serializing-json-manually-using-dartconvert).

## Caveats

- When an empty array is given, it will create a List<Null>. Such weird behaviour should warn the user that there is no data to extract.
- Equal structures are not detected yet (Equal classes are going to be created over and over).
- Properties named with funky names (like "!breaks", "|breaks", etc) or keyword (like "this", "break", "class", etc) will produce syntax errors.
- Array of arrays are not supported:

```json
[[{ "isThisSupported": false }]]
```

```json
[{ "thisSupported": [{ "cool": true }] }]
```
