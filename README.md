JSONStrings
===========
Restaurants: An array of key/value pairs 
* JSON array object name - "restaurants"
* Sample: http://130.191.3.5/~jayaprak/sdsuDining/restaurants.html
* Update the URL or key tags within the mobile app when necessary
* Key/Value pairs:
	* restaurant_id: Unique restaurant id
	* active: Boolean (true/false) restaurant status. Primarily used to determine if a location is still in business or not
	* lastModified: Last modified timestamp. Primarily used to prevent excessive database writes to the local mobile SQLite db 
	* restaurant_name: Restaurant's customer facing name
	* image: Restaurant image (logo) that needs to be displayed. String must match the image file name used within the app
	* location_id: Location id of the restaurant 
	* location_name: Location's customer facing name
	* phone: Restaurant's phone number
	* website: Restaurant's website URL
	
Hours: An array of key/value pairs
* JSON array object name - "hours"
* Each restaurant must have Monday through Sunday entries
* Sample: http://130.191.3.5/~jayaprak/sdsuDining/hours.html
* Update the URL or key tags within the mobile app when necessary
* Key/Value pairs:
	* id: Unique restaurant-day id
	* active: Boolean (true/false) hours status. Primarily used to determine if hours entry is still valid or not
	* lastModified: Last modified timestamp. Primarily used to prevent excessive database writes to the local mobile SQLite db 
	* restaurant_id: Unique restaurant id for which the hours entry is associated with
	* day: Monday-Sunday strings. Primarily used to associate the hours entry with a day
	* open: Opening time. Must follow a 12-hour clock followed by a space character and "AM" or "PM". Empty quotes ("") indicate always closed
	* close: Closing time. Must follow a 12-hour clock followed by a space character and "AM" or "PM". Empty quotes ("") indicate always closed
	
Coupons: An array of key/value pairs 
* JSON array object name - "coupons"
* Sample: http://130.191.3.5/~jayaprak/sdsuDining/coupons.html
* Update the URL or key tags within the mobile app when necessary
* Key/Value pairs:
	* coupon_id: Unique coupon id
	* active: Boolean (true/false) coupon status. This status must be scripted within the web service application. By comparing the coupon expiration date and the local timestamp of the webservice device, the script by return either "true" or "false" during the construction of the JSON object. This flag is primarily used to determine if a coupon is still valid or not
	* lastModified: Last modified timestamp. Primarily used to prevent excessive database writes to the local mobile SQLite db 
	* image: Coupon's image URL. This image URL will be displayed as the coupon
	* expiration: Coupon's expiration date
	
Farmer's Market: 
* JSON array object name - "farmersMarket"
* Sample: http://130.191.3.5/~jayaprak/sdsuDining/farmerMarket.html
* Update the URL or key tags within the mobile app when necessary
* Newline represented as "\n"
* Key/Value pairs:
	* id: Unique entry id
	* lastModified: Last modified timestamp. Primarily used to prevent excessive database writes to the local mobile SQLite db 
	* phone: Farmer's Market office phone number
	* fax: Farmer's Market office fax number
	* email:  Farmer's Market office email address 
	* website: Farmer's Market website URL
	* address: Farmer's Market physical location address
	* about: Short snippet explaining Farmer's Market
	
Catering: 
* JSON array object name - "catering"
* Sample: http://130.191.3.5/~jayaprak/sdsuDining/catering.html
* Update the URL or key tags within the mobile app when necessary
* Newline represented as "\n"
* Key/Value pairs:
	* id: Unique entry id
	* lastModified: Last modified timestamp. Primarily used to prevent excessive database writes to the local mobile SQLite db 
	* phone: Catering office phone number
	* fax: Catering office fax number
	* email:  Catering office email address 
	* website: Catering website URL
	* address: Catering physical location address
	* about: Short snippet explaining Catering
	
Sweet: 
* JSON array object name - "sweet"
* Sample: http://130.191.3.5/~jayaprak/sdsuDining/sweet.html
* Update the URL or key tags within the mobile app when necessary
* Newline represented as "\n"
* Key/Value pairs:
	* id: Unique entry id
	* lastModified: Last modified timestamp. Primarily used to prevent excessive database writes to the local mobile SQLite db 
	* phone: Sweet office phone number
	* fax: Sweet office fax number
	* email:  Sweet office email address 
	* website: Sweet website URL
	* address: Sweet physical location address
	* about: Short snippet explaining Sweet

Contact Us: 
* JSON array object name - "contactUs"
* Sample: http://130.191.3.5/~jayaprak/sdsuDining/contactUs.html
* Update the URL or key tags within the mobile app when necessary
* Newline represented as "\n"
* Key/Value pairs:
	* id: Unique entry id
	* lastModified: Last modified timestamp. Primarily used to prevent excessive database writes to the local mobile SQLite db 
	* phone: Contact Us office phone number
	* fax: Contact Us office fax number
	* email:  Contact Us office email address 
	* website: Contact Us website URL
	* address: Contact Us physical location address
	* about: Short snippet explaining Contact Us
	
PushNotification: GCM
* Sample: http://130.191.3.5/~jayaprak/sdsuDining/gcm/gcm.php
* Update the URL, Project Id, or message tag within the mobile app when necessary
* Please refer Android's GCM documentation for requirements and getting started basics such as creating a google project API, providing 3rd party applicaiton server IPs, etc: https://developer.android.com/google/gcm/index.html
* 3rd party application server skeleton suggestions:
	* Back-end db for storing regIds, encrypted ids preferred
	* Provide back-end db column of boolean (true/false) status on whether the device should receive push notifications
	* Mechanism to receive POST data from the mobile app containing the regId
	* User-facing web application with a text field to submit a push notification message
	* On message submit, perform an iterative POST of the message to the GCM servers containing the target information and parameters. Please refer: https://developer.android.com/google/gcm/server.html
