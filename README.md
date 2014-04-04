## NSDate+JavascriptTimestamp (works with Firebase)

###### A helper to convert back and forth between NSDates and Javascript formatted timestamps (millisecond timestamps)

Javascript creates timestamps in milliseconds, whereas Objective-C stores them in seconds since the epoch. We use firebase to handle our chat, where we store javascript timestamps of messages. In our iOS app we often need to convert back and forth to read/save timestamps to/from Firebase.

#### This is tested and working in production with our [Firebase](http://www.firebase.com) app [www.getbrandid.com](https://www.getbrandid.com)

## Usage

##### Create a new current javascript timestamp
        NSNumber *timestamp = [NSDate javascriptTimestampNow];

##### Convert a javascript timestamp to NSDate
        NSDate *aDate = [NSDate dateFromJavascriptTimestamp:timestamp];

##### Converting a javascript to NSDate from a Firebase snapshot
dateFromJavascriptTimestamp takes an (id), and works with Firebase formatted integers. Assuming you have a Firebase snapshot with a key of "timestamp" and value of 1396636109246

        NSDate *aDate = [NSDate dateFromJavascriptTimestamp:snapshot.value[@"timestamp"]];
        
##### Convert an NSDate to a javascript timestamp
        NSNumber *timestamp = [NSDate javascriptTimestampFromDate:aDate];
                
