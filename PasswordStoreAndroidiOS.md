# PasswordStore Android/iOS

## Introduction
This asset is a security password store for iOS/Android.
## Goodies
No keys on source code  
Write once run on both iOS/Android plathome  
Easy-to-use code similar to PlayerPrefs  
  
## Requirements
### iOS
iOS 8 to 11
### Android
KeyStore and RSA (Android 4.3 or later Excluding a few exceptions).

## Build Settings
### iOS(Keychain)
File -> Buid Settings -> Select "iOS" -> "Player Settings..." -> "Target minimum iOS Version" : "8.0" or later

Project -> Assets -> AMGPasswordStore -> Plugins -> iOS -> SAMKeychain -> Select "SAMKeychain.h" -> Inspector  -> Platfome Settings -> Framework Dependencies -> check "Security"

### Android(KeyStore)
File -> Buid Settings -> select "Android" -> "Player Settings..." -> "Minimum API Level" : "Android 4.3'Jelly Bean'(API Level 18)" or later 

## Location of crypted password data
### iOS
KeyChain fo iOS
### Android
Application Persistent DataPath/KeyName.AMGPrefs

## Manual
## Set password
### Set password string to store
AMGPasswordStore.AMGPrefs.SetString("KeyName","PasswordString");

### Set password int to store
AMGPasswordStore.AMGPrefs.SetInt("KeyName",p asswordInt);

### Set password float to store
AMGPasswordStore.AMGPrefs.SetFloat("KeyName", passwordFloat);

## Get password
### Get password string from store
AMGPasswordStore.string password = AMGPrefs.GetString("KeyName");

### Get password int from store
AMGPasswordStore.int password = AMGPrefs.GetInt("KeyName");

### Get password float from store
AMGPasswordStore.float password = AMGPrefs.GetFloat("KeyName");

### Get password string from store with default value
AMGPasswordStore.string password = AMGPrefs.GetString("KeyName", "DefaultString");

### Get password int from store with default value
AMGPasswordStore.int password = AMGPrefs.GetInt("KeyName", defaultInt);

### Get password foat from store with default value
AMGPasswordStore.float password = AMGPrefs.GetFloat("KeyName",defaultFloat);

## Delete key
### Delete one key
AMGPasswordStore.AMGPrefs.DeleteKey("KeyName");

### Delete all keys
AMGPasswordStore.AMGPrefs.DeleteAll();

## Has key
AMGPasswordStore.bool has = AMGPrefs.HasKey("KeyName");

## Dummy Method "Save()"
AMGPasswordStore.AMGPrefs.Save(); is dummy method.  
Saving automaticaly when you set password.  
It is using for migrate from PlayerPrefts to AMGPrefs.  
  
### Migrate example
// PlayerPrefs code  
using UnityEngine;  
public class Example : MonoBehaviour { 
    public void method1(){ 
        PlayerPrefts.SetString("KeyName", "Password"); 
        PlayerPrefts.Save(); 
    }  
}  
    
      
// Add namespace "using AMGPasswordStore;" and replace "PlayerPrefts" to "AMGPrefs".  
  
    
// AMGPrefs code   
using UnityEngine;  
using AMGPasswordStore;  
public class Example : MonoBehaviour { 
        public void method1(){ 
        AMGPrefs.SetString("KeyName", "Password"); 
        AMGPrefs.Save(); 
    }  
}  

