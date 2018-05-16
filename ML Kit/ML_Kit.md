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
  8. Tensorflow Lite model Serving
  9. Model compression and conversion service
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
    

ios. On-device image labeling

    vision = Vision.vision()

    let labelDetector = vision?.labelDetector()

    // set up image metadata ...

    let image = VisionImage(image: uiImage)

    labelDetector?.detect(in: image) { (labels, error) in

    guard error == nil, let labels = labels, !labels.isEmpty else {
    // ..
    return
  }
  // Handle extracted entities
  }
   
Android. On-device image labeling

    FirebaseVisionLabelDetector detector = FirebaseVision.getInstance().getVisionLabelDetector();

    FirebaseVisionImage image = FirebaseVisionImage.fromFilePath(context, uri):

    Task<List<FirebaseVisionLabel>> result = detector.detectImage(image).addOnSuccessListener(

      new OnSuccessListener<List<FirebaseVisionLabel>>() {
      @Override

        public void onSuccess(List<FirebaseVisionLabel> labels) {
          // Handle extracted entities
        })

      addONFailureListener(...);
})
    
 ###### For cloud image labeling
  change the name FirebaseVisionLable => FirebaseVisionCloudLabel etc

  Benifit of custom models
  1 - ML Kit API provides an API layer that interacts with our TensorFlow  Lite model so that we can provide input ouput
  just like we would do with the base APIs

  2 - We can upload the TensorFlow Lite model to the Firebase console and that provides two benifits
      1 - First is that we can bundle our model with our application, if we choose , but if its big and we want to reduce the install size, we can actually leave it to 
      the cloud and download it dynamically so the initial install size is smaller

  3 - And the third one , because it lives in the cloud we can dynamically switch the model. We don't have to submit a new APK or bundle to the App store or to the play store


  best property is remote config


  Load custom model 

    FirebaseCloudModelSource cloudSource = new 
    FirebaseCloudModelSource.Builder()
            .setModelName("my_model_v1")
            ...
            .build();

    What does remote config do is  we can dynamically change the value in out app , change background photo etc
    my_model_english
    my_model_spanish

  Load custom model using Remote Config

  FirebaseCloudModelSource cloudSource = new 
    FirebaseCloudModelSource.Builder()
            .setModelName(mFirebaseRemoteConfig.getString("my_model"))  # here we are using Remote Config to switch between models (like my_model_english and my_model_spanish)
            ...
            .build();


Compression/conversion of TF models
  Let's say I have tensorflow model and what I need is TensorFlow Lite model to run on device

  What we will do is , We would upload our TensorFlow model along with training data. And once its donw processing, We'll get TensorFlow Lite models

  Model Compression as a cloud service It takes hours of GPU's computation 

  like in FISHBRAIN  pretrained model 80MB 91.8% accuracy 
  after compression 7.1 MB 94.5% accuracy

