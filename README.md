## NSDate+JavascriptTimestamp

###### A helper to convert back and forth between NSDates and Javascript formatted timestamps (millisecond timestamps)

Javascript creates timestamps in milliseconds, whereas Objective-C stores them in seconds since the epoch. We use firebase to handle our chat, where we store javascript timestamps of messages. In our iOS app we often need to convert back and forth to read/save timestamps to/from Firebase.

#### Usage
