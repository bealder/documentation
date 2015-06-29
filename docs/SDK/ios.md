# BealderSDK for iOS

## Preparation

* 	Get your **appId** and **apiKey** from the [Bealder plateform)](http://app.bealder.com)

## Configure your project

*	Add the `BealderSDK.framework` and the `BealderSDK.bundle` into your project

* 	Add the required frameworks (`$YOUR_PROJECT -> $YOUR_TARGET -> Build Phases -> Link Binary With Libraries -> +`):
	- `MobileCoreServices.framework`
	- `SystemConfiguration.framework`
	- `AudioToolbox.framework`
	- `Social.framework`
	- `Accounts.framework`

*	Add `-ObjC` to your other linker flags (`$YOUR_PROJECT -> $YOUR_TARGET -> Build Settings -> Other Linker Flags`) if it's not already present.

*	In your info.plist file (`$YOUR_PROJECT -> $YOUR_TARGET -> Info -> Custom iOS Target Properties`), add the location update authorization description key `NSLocationAlwaysUsageDescription`. The value of this key must be the message the user will receive when the app will ask him for location update authorization (eg. *"We'll use location to send you interresting promotion based on your location"*)

*	In your app delegate header file, import the framework's header: 

	```objective-c
	#import <BealderSDK/BealderSDK.h>
	```

*	Add the delegate declaration in your app delegate's header like this:

	```objective-c
	@interface MyAppDelegate : UIResponder <UIApplicationDelegate, BealderDelegate>
	```

*	In your app delegate implementation file, in `-application:didFinishLaunchingWithOptions:`, start the session:

	```objective-c
	[[Bealder sharedSession] startSessionWithUUID:@"yourAppUniqueUUID" apiKey:@"yourBealderApiKey" appId:@"yourBealderAppId" delegate:self];
	```

	**Note:** If you don't need the delegate, you can remove it from your header file and pass `nil` to the delegate parameter of the latter method.

*	Add the push notification management:

	```objective-c
	- (void)application:(UIApplication *)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData *)deviceToken
	{
	    [[Bealder sharedSession] registerPushDeviceToken:deviceToken];
	}

	- (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)userInfo
	{
	    [[Bealder sharedSession] handleRemoteNotification:userInfo];
	}
	```

	**Note:** Don't call `-registerForRemoteNotificationTypes:` in your own code. It's called for you when you start the session. If you do, the SDK will generate an exception.

*	Stop the session when the app terminates:

	```objective-c
	- (void)applicationWillTerminate:(UIApplication *)application
	{
	    // Called when the application is about to end. Save data if appropriate. See also applicationDidEnterBackground:.
	    [[Bealder sharedSession] stop];
	}
	```

*	Then you can add the delegate methods if you need to do specific management with beacon detection:

	```objective-c
	#pragma mark - BealderDelegate

	- (void)bealder:(Bealder *)bealder didEnterRangeOfBeacon:(CLBeacon *)beacon
	{
		// The user enters the beacon area
	}

	- (void)bealder:(Bealder *)bealder didExitRangeOfBeacon:(CLBeacon *)beacon
	{
	    // The user quits the beacon area
	}

	- (void)bealder:(Bealder *)bealder didUpdateStateOfBeacon:(CLBeacon *)beacon
	{
	    // The beacon.proximity has changed
	}
	```

*	and errors:

	When an error occurs which prevents the SDK from working, the delegate set the `hasStopped` argument to `YES`. When it happens, you have to fix the problem, then call `[[Bealder sharedSession] restart]`:

	```objective-c
	- (void)bealder:(Bealder *)bealder didFailWithError:(NSError *)error hasStopped:(BOOL)hasStopped
	{
		NSString* restartButton = hasStopped ? NSLocalizedString(@"Restart", nil) : nil;
	    UIAlertView* alertView = [[UIAlertView alloc] initWithTitle:NSLocalizedString(@"Error with Bealder SDK", nil) message:error.localizedDescription delegate:self cancelButtonTitle:NSLocalizedString(@"OK", nil) otherButtonTitles:restartButton, nil];
	    [alertView show];
	}

	#pragma mark - UIAlertViewDelegate

	- (void)alertView:(UIAlertView *)alertView clickedButtonAtIndex:(NSInteger)buttonIndex
	{
	    if (buttonIndex == 1) // Restart
	    {
	    	// Restart the SDK
	        [[Bealder sharedSession] restart];
	    }
	}
	```

## Errors

Here is a list of all the errors the SDK can return to your app with the error domain `BLDBealderDomainError`:

Error                                  | Code         | Stop the SDK? | Description
---------------------------------------|--------------|---------------|-------------------------------------------------------------
`BLDErrorCodeNoNetworkAvailable`       | `-1009`      |      YES      | The device is in plane mode or has no network available
`BLDErrorCodeBealderServerUnreachable` | `-1003`      |      YES      | The Bealder server is not available over the current available networks
`BLDErrorCodeNoBluetoothEnabled`       | `-8713`      |      YES      | Bluetooth is not activated on the device or the device is not compatible
`BLDErrorCodeCorruptedServerResponse`  | `3840`       |      YES      | The Bealder server returned a malformed response
`BLDErrorCodeRequestTimedOut`          | `-1001`      |      YES      | The request to the Bealder server timed out
`BLDErrorCodeUnregisteredBeacon`       | `-111000111` |       NO      | The detected beacon is not registered on the Bealder server
`BLDErrorCodeUnregisteredDeviceForPush`| `-1404` 	  |      YES      | No push server registered for this device
`BLDErrorCodeLocationAccessRefused`    | `-695`       |      YES      | The user hasn't allowed location updates for the app
`BLDErrorCodeServerCrashed`            | `-500`       |      YES      | The Bealder webservice crashed while answering a request
`BLDErrorCodeUnknown`                  | `-42`        |      YES      | Unknown error! #CaptainObvious

If you need more information about the error, you can delve into the sub errors via the `userinfo`'s `NSUnderlyingErrorKey` like in the exemple below:

```objective-c
NSError* currentError = error;
while (currentError)
{
    NSLog(@"%@", currentError);
    currentError = currentError.userInfo[NSUnderlyingErrorKey];
}
```

