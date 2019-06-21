# FCM
Initial

1> Create blank project

1.1> Login in your Android Studio.

2> Go to Tool
  i> Select Firebase
  ii> Connect your app to firebse
  iii> Add FCM to your app

3> Add dependencies 

dependencies {

    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation 'androidx.appcompat:appcompat:1.0.0'
    implementation 'androidx.constraintlayout:constraintlayout:1.1.3'
    implementation 'com.google.firebase:firebase-messaging:19.0.0'
    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'androidx.test:runner:1.1.0'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.1.0'
    implementation 'com.google.firebase:firebase-core:17.0.0' 
    }
    
    
4> Go to Studio 
   Refactor -> Migrate to AndroidX

5> Clean And Rebuild

6> Implement "FirebaseMessagingService"

7> Ovverride method "onRecive"

8> You get all notification in this method and you have to implement "NotificationCompat.Builder" to show in device

9> you have to add this code in MaainActivity.java to catagorige (like "Paid", "Free", here "general" is catagorie)




           FirebaseMessaging.getInstance().subscribeToTopic("general")
                .addOnCompleteListener(new OnCompleteListener<Void>() {
                    @Override
                    public void onComplete(@NonNull Task<Void> task) {
                        String msg = "Successfull";
                        if (!task.isSuccessful()) {
                            msg = "Faield";
                        }

                        Toast.makeText( MainActivity.this, msg, Toast.LENGTH_SHORT).show();
                    }
                });
                
                
                
                
 10 > open https://console.firebase.google.com/
 
 11 > 
 
    i> Create Notification
    
    ii> Add Title & Text
    
    iii> Terget -> select app and topic ("general")
    
    iv> Additional option -> Add Chennel Name "MyNotifications" 
    
    v> Send.
    
    
<h1><b>If you select topic it takes 24 hrs to live / without topic it appear immediately in device 


