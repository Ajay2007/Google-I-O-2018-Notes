## ML Kit for building machine learnign app for android.
Add machine learnign to your apps to solve real world problems.

TensorFlow Lite
A  ligjtweight machine learning library and tools for mobile and embedded devices.

ML Kit  is a google machine learning sdk for mobile devices

These are Neural Networks APIs

1. ML kit is both for android as well as ios app.
2. Base APIs and custom model support
3. On-device and Google Cloud AI inference APIs
4. Deeply integrated with firebase  (it works other features of firebase)

Base APis 
Simple APIs that solve practical use cases
  1. Text recognition
  2. Image Labeling
  3. Barcode Scanning
  4. Face detection
  5. Landmark recognition
  6. High density face contour feature and smart reply API () Same technology use in wear os
  7. We can upload ML model to the firebase console 
  
Custom Modle Support
  Simplify use of custom ML model
  Dyanmic model downloads
  A/B testing via Firebase Remote Config
  Model conversion and compression (IT will help us to convert full tensorflow model into lightweight tensorflow model)
  
 Companies that helped to make ML kit succed are 
  EyeEm
  intuit turbotax
  vsco
  PicsArt
  FISHBRAIN
  Lost It!
  
 PIcsArt => The PicsArt team uses ML Kit for there Magic Effects, an 
 artistic style transfer photo effects. The SDK provided a number of benifits includeing 
 cross-platform compatibility and small SDK size.
 
 turbotax => At TruboTax , there are always looking for ways to make doing
 taxes license 2D barcode scanning feature from ML Kit , they enabled customers to 
 easily scan their license and pre-populate their information, reducing 
 manual data entry and potential for error. Ml Kit was easy to integrate and deploy.
 
 ### How ML Kit Works
little bit about firebase
  Storage
  real time database
  firestore
  remote config
  crashlytics
  analytics
  EB Testing
  
  #### One Feature Example of Machine learnign Kit 
    Image Labeling API
    
    Free for mobile Low latency No Network required 400 + labels
    cloud based - Free for 1000 API calls per feature per month then paid
    benifit of cloud based API is High-accuracy classification and 10000 + labels
    
    Including libraries int he build files
    for Ios
      Podfile
        pod 'Firebase/Core'
        pod 'Firebase/MLVision'
        pod 'Firebase/MLVisionLabelModel' # on device model
        
     build.gradle
        dependencies {
        // ...
        implementation 'com.google.firebase:firebase-core:15.+'
        implementation 'com.google.firebase:firebase-m1-vision:15.+'
        implementation 'com.google.firebase:firebase-m1-vision-image-label-model:15.+' # on devide model
        apply plugin: 'com.google.gms.google-sevices'
    
    
    
    
    
    
    
  
  
