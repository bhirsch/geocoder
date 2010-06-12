// $Id$

Geocoder
________

To install, place the entire Geocoder folder in your modules directory. 
Go to Administer -> Site configuration -> Geocoder.
Save your Google Maps API Key and Sunlight Labs API key.

If you do not have keys yet, you can get them here:
Google Maps: http://www.google.com/apis/maps/
Sunlight Labs: http://services.sunlightlabs.com/api/register/

If you want Geocoder to automatically tag each geocoded address with related district/legislator information, check the box "Apply district taxonomy terms." This feature requires installation of the District module.

Geocoder needs permission to create CSV files inside the csv_files directory (which comes inside the geocoder folder). If you get a 'permission denied' error when running Geocoder, chmod 777 csv_files. Then try again. That should fix it.

Note: The ONLY thing that should be stored in csv_files is csv files created by Geocoder. This folder would be an insecure place to put any sensitive information, like passwords, etc.


Administration
______________

Go to Administer -> Geocoder.
Here you will see a list of Batches of Addresses that have been submitted. In the Geocoded column you can see clearly which batches have been processed (yes) or not (no). Follow the "Process Batch" link (admin/geocoder/%) to process a selected batch.

On the Process Batch page you will see info at the top about the batch being processed. Below those details are statistics to tell you how processing is coming along. Below the stats are processing buttons.

Processing a batch includes three steps (each step just requires a button click):
1. Geocode addresses
2. Get districts and legislators
3. (If the user opted for this) Create nodes fore each address

The reason this is broken into 3 steps, rather than have processing run automatically, is that with large batches Google and Sunlight Labs both time-out sometimes. This way, you can run Geocode a few times if you need to. Then run Get Districts a few times. And you can be sure that each record gets coded. It's easy to follow the progress by watching the statistics which tell you how many records are in your batch, how many have been geocoded, how many have been district/legislator coded, and how many have been turned into nodes.