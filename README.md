
# mim-OE-SE-iOS

**mim OE (mim Operating Environment)**, mim-OE-SE-iOS Standard Edition for Apple iOS.

## Before You Start

- [Explore developer resources & documentation](https://developer.mimik.com)
- [Sign up and create a mimik developer console account](https://developer.mimik.com/console/create_account)
- [Follow the Integrating the mimik Client Library into iOS project guide](https://devdocs.mimik.com/tutorials/01-submenu/02-submenu/02-index).
- [Learn the basics of Working with mimOE in an iOS project](https://devdocs.mimik.com/tutorials/01-submenu/02-submenu/03-index).


## Installation Guide

To get started, simply add a configuration such as this to your `Podfile`:


```swift
platform :ios, '16.0'
source 'https://github.com/CocoaPods/Specs.git'
source 'https://github.com/mimikgit/cocoapod-edge-specs.git'

use_frameworks!
inhibit_all_warnings!

def mimik
  pod 'EdgeCore'
  pod 'mim-OE-ai-SE-iOS-developer'
end

target '{target}' do
  mimik()
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['VALID_ARCHS'] = '$(ARCHS_STANDARD_64_BIT)'
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '16.0'
      config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'YES'
    end
  end
end
```

## Documentation

`EdgeCore/EdgeClient` API reference documentation can be found  [here](https://mimikgit.github.io/cocoapod-EdgeCore/documentation/edgecore/edgeclient).

`EdgeEngineClient` platform protocol API reference documentation is [here](https://mimikgit.github.io/cocoapod-EdgeCore/documentation/edgecore/edgeengineclient).

`EdgeService` API references are available [here](https://mimikgit.github.io/cocoapod-EdgeService/documentation/edgeservice/).

## Tutorials

After installation, try the following tutorials:

- [Understanding the mimik Client Library for iOS](https://devdocs.mimik.com/key-concepts/10-index).
- [Creating a Simple iOS Application that Uses an edge microservice](https://devdocs.mimik.com/tutorials/01-submenu/02-submenu/01-index).
- [Integrating the mimik Client Library into an iOS project](https://devdocs.mimik.com/tutorials/01-submenu/02-submenu/02-index).
- [Working with mimOE in an iOS project](https://devdocs.mimik.com/tutorials/01-submenu/02-submenu/03-index).
- [Working with edge microservices in an iOS project](https://devdocs.mimik.com/tutorials/01-submenu/02-submenu/04-index).
