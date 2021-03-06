# EZKeychain

[![CI Status](https://img.shields.io/travis/PattoMotto/EZKeychain.svg?style=flat)](https://travis-ci.org/PattoMotto/EZKeychain)
[![Version](https://img.shields.io/cocoapods/v/EZKeychain.svg?style=flat)](https://cocoapods.org/pods/EZKeychain)
[![License](https://img.shields.io/cocoapods/l/EZKeychain.svg?style=flat)](https://cocoapods.org/pods/EZKeychain)
[![Platform](https://img.shields.io/cocoapods/p/EZKeychain.svg?style=flat)](https://cocoapods.org/pods/EZKeychain)

## Description

Lightweight [Keychain API](https://developer.apple.com/documentation/security/keychain_services) wrapper.
Yes this just another one :)

You may wanna check this cool [Keychain wrapper](https://github.com/evgenyneu/keychain-swift)

## Example

```swift
let keychain = EZKeychain.shared

keychain.writeString(key: keyString, value: "Simple string")
print(keyString, keychain.readString(key: keyString))
keychain.clear(key: keyString)

keychain.write(key: keyCodable, value: FooBarStruct(foo: "Foo", bar: 11))
let foobar:FooBarStruct? = keychain.read(key: keyCodable)
print(keyCodable, foobar)
keychain.clear(key: keyCodable)

keychain.writeData(key: keyData, value: NSKeyedArchiver.archivedData(withRootObject: [111.11, 999.99]))
print(keyData, keychain.readData(key: keyData))
keychain.clear(key: keyData)

keychain.writeObject(key: keyObject, value: ["Foo": 111.11])
print(keyObject, keychain.readObject(key: keyObject))
keychain.clear(key: keyObject)
```

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

## Installation

EZKeychain is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'EZKeychain'
```

## Author

PattoMotto

## License

EZKeychain is available under the MIT license. See the LICENSE file for more info.
