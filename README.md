# sixth_sense_v0.1


#SixthSense

##A wearable gesture interface

README
------

Check out the [TED video](http://www.ted.com/talks/pranav_mistry_the_thrilling_potential_of_sixthsense_technology.html) to get a good idea of what the project is about.

For more information on SixthSense software and hardware, see:

 <http://code.google.com/p/sixthsense/wiki/Software>

 <http://code.google.com/p/sixthsense/wiki/Hardware>

Detailed documentation is in progress.

64-bit users!
-------------

There are currently some problems plaguing 64 bit systems that we're trying to
fix. Until then, follow these steps to debug the code under 64-bit systems (in
Visual Studio):

1. From top menu select "Build", then "Configuration Manager". After adding a
new "x86" platform inherited from debug platform, we see a new platform in the
list and the old one is removed. 

2. From the new platform displayed we click on Platform column to see a
dropdown containing 3 options "or more", the first is "Any CPU", the second is
<New...>, and the third is <Edit...>, select <New...>, a window will
open to choose the platform.

3. Select x86 then hit OK.

4. Click debug, it runs as it should.

Mailing List
------------

This is where most of the discussion goes on.

<http://groups.google.com/group/ss_dev>

**Please read the rest of this README before asking a question on the mailing list**

Technology
-----------

We use C# (tested on Windows, not Mono) with OpenCV (for .NET).

Developers
----------

To get started, there's all kinds of indentation issues in the codebase, fix
those so you can get a feel for how all the code is laid out.

Errors Fixation 
----------------

1.  Replace in app.config:

<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup>
with 

<startup useLegacyV2RuntimeActivationPolicy="true">
   <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/>
</startup> 




2.  Unable to load DLL 'System.Xaml.dll':

     Go to C:\Windows\Microsoft.NET\Framework64\v4.0.30319 and locate System.Xaml.dll

3.   Unable to load DLL 'WebCamLib.dll':
     
     Make sure WebCamLib.dll is present in C:\Windows\System32, if not present copy it from the debug folder to system32 in Windows


4. WpfUserControl_Mail01.UserControl1 Control_mail = new WpfUserControl_Mail01.UserControl1(); :: Unreference Error

  Solve by commenting out this line  and replacing with

  WpfUserControl_Mail01.UserControl1 Control_mail;



5. the type or namespace name 'directx' does not exist in the namespace 'microsoft'
     
      This was deprecated a long time ago. The last Direct SDK that still has the managed wrappers is February 2010. The download is available in link given below. You'll get to pick the references you are looking for after you install that one.

      Link is  http://www.microsoft.com/en-us/download/details.aspx?id=10084

 
       Go to "Add refference" dialog press "Browse" , go to something like this "C:\Windows\Microsoft.NET\DirectX for Managed Code\1.0.2902.0" or "C:\Windows\Microsoft.NET\Managed DirectX\v9.02.2904" then choose proper dll for example - Microsoft.DirectX.dll. So you can add "using Microsoft.DirectX" directive to your project.




       For any other queries :

        Mail me @ tiwari.anurag126@gmail.com




