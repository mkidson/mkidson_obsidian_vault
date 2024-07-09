https://github.com/mkidson/jazzfest_scanner

A plan to create a webapp for scanning student codes at jazz fest. I'd like to make it so that you can select where you are and either what time you're scanning for or it just sends the time and we can work it out later. 
It should send the data directly to a google sheet (requires constant connection but that would be true for accessing the webapp and I don't think we have Wi-Fi problems on DSG campus)

# Look at Google Firebase


# The webapp
Looking at using [Budibase](https://budibase.com/) or just building some backend from Python as that might be easier really, given that it's such a simple operation. 


# The reader
Using [this scanner](https://github.com/mebjas/html5-qrcode?tab=readme-ov-file) which handles it all nicely. When it scans, I've made it pop up with a `window.alert` so it won't scan until you press "OK". Then need to find out how to send that text to the python stuff. 

Want to use some logic so that it only sends if it starts with `NYJF` or similar.

# The link to google sheets
I've set up a google sheets API thing. Using the [spreadsheets.values.append](https://developers.google.com/sheets/api/reference/rest/v4/spreadsheets.values/append) function to append to a bunch of rows. Might come up against an issue of API request rates. It has a limit of 100 per 5 mins. 

# Generating codes
Looks like there are a few options for generating the codes in bulk. I've had a look at [qr batch](https://qrbatch.io/free-bulk-qr-code-generator.html) and it seems good but needs a payment for more than 50 codes. I think it should work to do `NYJF240001` as the format, where the `24` is the year, and the last 4 digits are the unique code.



# Running
I'm thinking of making a few dropdowns, for the session, place, etc, and then a button to scan, so the scanner only interprets the image if asked. If it successfully detects a QR code, then it sends the data off, otherwise it throws an error like "No QR code found, scan again"

