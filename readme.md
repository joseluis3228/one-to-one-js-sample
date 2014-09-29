# Sightcall JavaScript One To One Sample 


This is an example of a bare-bones sightcall installation

For a full JavaScript API reference please refer to our [official documentation website](https://docs.sightcall.com/GD/01_javascript/).

- [Quick-start RtccDriver and WebRTC](https://docs.sightcall.com/GD/01_javascript/01_jsquickstart.html)


### How to deploy the examples

##### Requirement

- It is important that the project is served from a webserver and not from the file system when using WebRTC.
- Be aware of your AppId, and understand what is a ```UID``` and a ```Display Name```. All of them are described in our [definition page](https://docs.sightcall.com/GD/06_definitions.html).

You can find more details about AppID, UID and Display Name [here](https://docs.sightcall.com/GD/01_javascript/01_jsquickstart.html)

You also need to be able to get tokens out of the weemo cloud. The fastest way to obtain a token is to use one of our Authentication Client for backends. Description and samples are available [here](https://docs.sightcall.com/GD/04_backend/).

##### Setting up the AppID and the Authentication URL

Once you have received your ```AppID``` provided by Sightcall, you can setup these examples with your AppId in order to test the API. The only thing you have to do is to setup the ```AppId``` as well as the Authentication URL.
To do so, for each of the Javascript examples you want to use, you must edit the .html file and
replace the placeholder "YOUR_APP_IDENTIFIER" by your AppID in the following lines"

```html
<script type="text/javascript" src="https://download.rtccloud.net/js/webappid/YOUR_APP_IDENTIFIER"></script>
```

and 

```JavaScript
var rtcc = new Rtcc("YOUR_APP_IDENTIFIER", "callee_uid", "internal", options);
```

You also need to replace the following line if you are using our java, node.js or ruby Authentication API Client sample:

```
//AUTH_URL = 'http://YOUR_AUTH_URL/gettoken?uid=',
```
 or if you are using our PHP Authentication API Client Sample.

```
// AUTH_URL = 'http://YOUR_AUTH_URL/gettoken.php?uid=',

```
In any case, you have to uncomment the right line and specify the URL where a token can be found by the web page.
Of course, if you have implemented your own client parameters and URL might be different and you need to update the samples accordingly.

Now you can upload the examples on a webserver and start using them.

##### One-to-one example

In this example, the ```UID``` and ```Display Name``` are already set. 
In the caller.html, you will be connected using caller_uid as a ```UID``` and  Caller as a ```Display Name```, and if you are using callee.html, you will be connected using callee_uid as a ```UID``` and Callee as a ```Display Name```.

>You can find more details about ```AppID```, ```UID``` and ```Display Name``` [here](https://docs.sightcall.com/GD/01_javascript/01_jsquickstart.html)


#### How to use  

This example is composed of four html files. Three of them called ``caller*.html``` and the other one named ```callee.html```. With all files a user called ```callee_uid```logged in the callee.html file connects and can be joined by a caller.  
In order to initiate a call between these two pages here a the steps you have to follow:

- Open ```callee.html``` in one computer and wait te be connected. You will know that you are connected when you will see these sentences appear in your browswer:

```JavaScript
Connected as Callee using (RtccDriver|WebRTC).
Waiting for a call.
```

- At this moment open the ```caller.html``` in another computer and wait  to be connected. You will know that you are connected when you will see the following sentence appears in your browser as well as a button labeled **'Click to call Callee'**:

```JavaScript
Connected as Caller using (RtccDriver|WebRTC)
```

- Click the button **'Click to call Callee'** in the ```caller.html``` page in your browser. The call is initiated.
- Answer the call in the ```callee.html``` page and the Video Chat starts.

>Warning: If using WebRTC, you will be ask to allow access to your microphone and camera when initiating a call and when accepting a call. Click ```Allow``` in order to give WebRTC access to these peripherics. 


#### Managing an external caller

If you wish to use external users, instead of using the page ```caller.html```, just use the page ```caller_external.html```. In that case, the caller is not an authentified user but an external one, attached to the premium user callee_uid, and only allowed to call that premium user.  
The behaviour of the external in the example is exactly the same as before. Please note that you have a limited number of external calls allowed.

#### Managing auto-start calls

The last case is pretty much the same except that the caller will automatically call when the connected to the cloud. It is availbale through the ```caller_external_automatic.html```. Automatic calls can be done either with internal or external users. 

>Warning: Please note that the call starts when the caller page receives the ```sipOK```notification and that the call has not been done yet. That notification is regularly sent to the application to keep it informed that the client is still connected the RTCC cloud and can be reached.
