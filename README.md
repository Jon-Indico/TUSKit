# TUSKit
[![Protocol](http://img.shields.io/badge/tus_protocol-v1.0.0-blue.svg?style=flat)](http://tus.io/protocols/resumable-upload.html)
[![Version](https://img.shields.io/cocoapods/v/TUSKit.svg?style=flat)](http://cocoadocs.org/docsets/TUSKit)
[![License](https://img.shields.io/cocoapods/l/TUSKit.svg?style=flat)](http://cocoadocs.org/docsets/TUSKit)
[![Platform](https://img.shields.io/cocoapods/p/TUSKit.svg?style=flat)](http://cocoadocs.org/docsets/TUSKit)

An iOS client written in `Objective-C` for [tus resumable upload protocol](http://tus.io/).

## Pull Requests
Pull requests are always welcome! However, please submit a PR to the `development` branch in order to keep the `master` branch match up with the `TUSKit` pod at all times.

## Installation

TUSKit is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

    pod "TUSKit"

## Example Project
To run the example project, clone the repo, and run `pod install` from the Example directory first. 

## The Protocol
You'll need a tus.io friendly server before using TUSKit or any other tus client. You can find a list of [tus implementations here](http://tus.io/implementations.html).


# Usage (1.3.0)
------
## TUSSession
A NSURLSession that manages, creates, and reloads TUS uploads using a single NSURLSession and data store.
    
    ...
    @property (strong, nonatomic) TUSSession *tusSession;
    ...
    ...
    self.tusSession = [[TUSSession alloc] initWithEndpoint:[[NSURL alloc] initWithString:UPLOAD_ENDPOINT] dataStore:uploadStore allowsCellularAccess:YES];

**Endpoint** - An NSURL of your tus.io server.

**dataStore** - The `TUSUploadStore` you've created for your uploads.

**allowsCellularAccess** - Allow uploads over cell data.


## TUSUploadStore
The data storage for uploads.

    TUSUploadStore * uploadStore = [[TUSFileUploadStore alloc] initWithURL:[applicationSupportURL URLByAppendingPathComponent:FILE_NAME]];

**URL** - URL To Local File.

## TUSResumableUpload
Easily add uploads to your data storage using the your TUSSession.

    TUSResumableUpload *upload = [self.tusSession createUploadFromFile:fileUrl headers:@{} metadata:@{}];


**fileUrl** - URL To Local File.

*Headers** - An `NSDictionary` of your custom headers for the upload.

**Metadata** - 



# Usage
------
Please refrence the Example Project for usage examples while documentation is being written.


# About [tus.io](http://tus.io):
------
  Users want to share more and more photos and videos. But mobile networks are fragile. Platform APIs are a mess. Every project builds its own file uploader. A thousand one week projects that barely work, when all we need is one real project, done right.

  We are going to do this right. We will solve reliable file uploads for once and for all. A new open protocol for resumable uploads built on HTTP. Simple, cheap, reusable stacks for clients and servers. Any language, any platform, any network.

TUSKit is a ready to use tus client for iOS.


# License
------
TUSKit is available under the MIT license. See the LICENSE file for more info.

