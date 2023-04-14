# AllDocReader_public

[![](https://jitpack.io/v/tariqzia7523/MyDocReaderLib.svg)](https://jitpack.io/#tariqzia7523/MyDocReaderLib)

This project contains library for reading almost every kind of file, xls, doc ppt and almost every other. 

# implementation
Add flowing in 
    
    maven { url 'https://jitpack.io' }

then following line in app gradle

     implementation 'com.github.tariqzia7523:MyDocReaderLib:Tag'

# Usage

Add Following Tag in app's manifest 
    
    <activity
            android:name="com.xls.bbbbb.office.OpenFileActivity"
            android:exported="true"
            android:screenOrientation="portrait"
            tools:ignore="LockedOrientationActivity">
    </activity>

Call this activity and pass filePath like following

     val intent = Intent()
     intent.setClass(this@MainActivity, OpenFileActivity::class.java)
     intent.putExtra(MainConstant.INTENT_FILED_FILE_PATH, fileModel.filePath)
     startActivityForResult(intent, RESULT_FIRST_USER)

You may call it like 

     startActivity(Intent(this@MainActivity,OpenFileActivity::class.java).putExtra(MainConstant.INTENT_FILED_FILE_PATH, fileModel.filePath))

## you may use this as 

This lib can give you list of any required document type you may use following code. Its good to use it in another thread

     try{
         val list : ArrayList<FileModel> = FileListUtils.getExternalFileList(this@MainActivity, MimeTypeMap.getSingleton().getMimeTypeFromExtension("docx")!!)
     }catch (e : Exception){
        e.printStackTrace()
     }

And FileModel class is 

    class FileModel(var displayName : String, var fileUri : Uri, var filePath : String) {}

GoodLuck
