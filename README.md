AndroidEmailIntent
==================

Android intent to call system Email-client to send mail


Android Intent, the object carrying an intent that is  
message from one component to another component with-in the application or outside the application.  
  
you don't always need to build a e-mail application from the scratch, most of the android devices comes with the
ready to mail client or imap and pop3 email clients in the operating system for sure. all you need to know is the
simple way to connect your appliction to the system mail client. doing this in your application saves the time in
building the email activity for you and other features that any email app would take to build.
**Advantage**  
-> You will save noticeable amount of time.
-> Features of the system mail client application will have multiple features and more.
  
**Disadvantage**
-> You can't log the mail activity you did in the system mail client.
-> You need to login to the system app or email account for tracking your mails.

  
** Implementaion and objects to work with **
  
**Intent Object - Action to send Email**  You will use ACTION_SEND action to launch an email client installed on   
your Android device. Following is simple syntax to create an intent with ACTION_SEND action.  

     Intent emailIntent = new Intent(Intent.ACTION_SEND);

**Intent Object - Data/Type to send Email** To send an email you need to specify mailto:  
as URI using setData() method and data type will be totext/plain using setType() method as follows:
  
      emailIntent.setData(Uri.parse("mailto:")); 
      emailIntent.setType("text/plain");

**Intent Object - Extra to send Email** Android has built-in support to add TO, SUBJECT, CC, TEXT etc. fields which can be  
attached to the intent before sending the intent to a target email client. You can use following extra fields in your email:  

      EXTRA_BCC       --A String[] holding e-mail addresses that should be blind carbon copied.  
      EXTRA_CC        -- A String[] holding e-mail addresses that should be carbon copied.  
      EXTRA_EMAIL     -- A String[] holding e-mail addresses that should be delivered to.   
      EXTRA_HTML_TEXT --A constant String that is associated with the Intent, used with ACTION_SEND to   
                          supply an alternative to EXTRA_TEXT as HTML formatted text.
      EXTRA_SUBJECT   -- A constant string holding the desired subject line of a message. 
      EXTRA_TEXT      --  A constant CharSequence that is associated with the Intent, used with **ACTION_SEND**  
                         to supply the literal data to be sent.
      EXTRA_TITLE     --A CharSequence dialog title to provide to the user when used with a ACTION_CHOOSER. 

**Here is an example showing you how to assign extra data to your intent:**  
     emailIntent.putExtra(Intent.EXTRA_EMAIL , new String[]{"ashu@example.com"});   
     emailIntent.putExtra(Intent.EXTRA_SUBJECT, "subject of email");   
     emailIntent.putExtra(Intent.EXTRA_TEXT , "body of email");  
     
![screen1](https://github.com/ashokslsk/AndroidEmailIntent/blob/master/Screens/s1.png)
![screen2](https://github.com/ashokslsk/AndroidEmailIntent/blob/master/Screens/s2.png)
