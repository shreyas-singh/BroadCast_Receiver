# BroadCast_Receiver
In this project i will be writing code about Broadcast Receivers. 

Broadcast Receivers introduction.
-- Broadcast Receivers are used for responding to a broadcasted message(events). The event which are triggered are intent. Intents are broadcasted with an action name associated with them. Broadcast receivers responds to intents which have the same action name as that of broadcast receiver intent filter action name ( they also check category name , permissions and wether theyare in the scope of the broadcast )

Broadcast receivers can be initialized in 2 ways.
  1- Using the <receiver> </receiver> tag in the manifest file where within the tag we mention permissions ( these could be custom permissions or system genrated permissions ) , action names using intent filter and exported tag ( this is used when we want the receiver to receive broadcast's whch are broadcated in the app only , no any other broadcast )
  example : we can have a broadcast receiver declared in the manifest file like this 
  <receiver android:name=".MyBroadcastReceiverExample"  android:exported="true"
  android:permission="android.permission.SEND_SMS"
  >
    <intent-filter>
        <action android:name="android.intent.action.BOOT_COMPLETED"/>
        <action android:name="some_custom_action_name" />
    </intent-filter>
  </receiver>
So in this example , our broadcast receiver is registered to receive broadcasts from other apps or from system also ( android:exported="true" )
Also , our broadcast receiver will respond to intents that have action name - android.intent.action.BOOT_COMPLETED and some_custom_action_name 
Also , our receiver will receive only those broadcasts whose sender has been granted the permision - android.permission.SEND_SMS .

This is the first way of registering the receiver
