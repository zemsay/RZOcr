# RZ OCR library

- How to add the library?
  
  Add following code snippet in your root `build.gradle` file
  
       allprojects {
          repositories {
              jcenter()
              maven { url "https://jitpack.io" }
          }
        }

      dependencies {
        ...
        classpath 'com.github.dcendents:android-maven-gradle-plugin:1.4.1'
        ...
      }
        
 Add following code snippet in your app `build.gradle` file
 
    dependencies {
      ...
      compile 'com.github.zemsay:RZOcr:v1.0.2'
      ...
    }

# Sample Usage

Add following code snippet for initialization
  
    Intent intent = new Intent("com.zemsay.ocr");
    this.startActivityForResult(intent, REQUEST_CODE);
 
Add following code snippet for OCR Result callback.
 
    @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        if(requestCode == REQUEST_CODE)
        {

                String message = data.getStringExtra("OCR_RESULT");
                ((TextView) findViewById(R.id.ocr_result_text)).setText(message + "");


        }
    }





