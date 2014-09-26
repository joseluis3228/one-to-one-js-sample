# Sightcall JavaScript API examples 


This is an example of a bare-bones sightcall installation

For a full JavaScript API reference plese refer to our official documentation website : [http://docs.sightcall.com/js](http://docs.sightcall.com/js) and refer to our Github documentation:

- [Quick-start RtccDriver and WebRTC](https://docs.sightcall.com/GD/01_javascript/01_jsquickstart.html)


### How to deploy the examples

##### Requirement

- It is important that the project is served from a webserver and not from the file system when using WebRTC.
- Be aware of your AppId, and understand what is a ```UID``` and a ```Display Name```

You can find more details about AppID, UID and Display Name [here](https://docs.sightcall.com/GD/01_javascript/01_jsquickstart.html)

##### Setting up the AppID

Once you have received your ```AppID``` provided by Sightcall, you can setup these examples with your AppId in order to test the API. The only thing you have to do is to setup the ```AppId```.
To do so, for each of the Javascript examples you want to use, you must edit the .html file and
replace the placeholder "YOUR_APP_IDENTIFIER" by your AppID in the following lines"

```html
<script type="text/javascript" src="https://download.rtccloud.net/js/webappid/YOUR_APP_IDENTIFIER"></script>
```

and 

```JavaScript
var rtcc = new Rtcc("YOUR_APP_IDENTIFIER", "callee_uid", "internal", options);
```

Now that you have setup the AppId you can upload the examples on a webserver and start using them.

##### One-to-one example

In this example, the ```UID``` and ```Display Name``` are already set. 
In the caller.html, you will be connected using caller_uid as a ```UID``` and  Caller as a ```Display Name```, and if you are using callee.html, you will be connected using callee_uid as a ```UID``` and Callee as a ```Display Name```.

>You can find more details about ```AppID```, ```UID``` and ```Display Name``` [here](https://docs.sightcall.com/GD/01_javascript/01_jsquickstart.html)


#### How to use  

this example is composed of two html files. One called **caller.html** and the other one named ```callee.html```. In order to initiate a call between these two pages here a the steps you have to follow:

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

