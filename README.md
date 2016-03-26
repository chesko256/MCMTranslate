# MCM Translate
A utility for machine translating English SkyUI MCM Translation files into all other supported languages using Google Translate.

Usage
=====
    python MCMTranslate.py [English MCM translation file] | [--help]
    [English MCM translation file]: UTF-16 LE with BOM encoded MCM translation file ending in 'english.txt'
    --help: Shows this help message.

Instructions
============
1. Clone this repository.
2. Install Python 2.7 or newer.
3. Install `pip`, if necessary. https://pip.pypa.io/en/stable/installing/
4. Install the Google Translate API Client Library for Python.    

    `pip install --upgrade google-api-python-client`    

5. Set up a Google Developer Console project named 'mod translate', or whatever you like. https://console.developers.google.com. Within the project, create a new application. Name it whatever you like.
6. In the Google Developer Console slide-out menu, go to API Manager > Translate API, and select Enable.
7. In the sidebar, select Credentials, and select Create credentials > API key. Create a 'server key'.
8. Create a file named `google_api_secret.txt` in the same directory as MCMTranslate.py. Copy and paste the generated API key into the text file. **Do not share this key with anyone, as it handles billing and quotas. You have been warned.**
9. In the Google Developer Console slide-out menu, go to Billing and create a billing account.
10. **IMPORTANT**: In the sidebar, go to Budgets and Alerts and create a budget for the project. I set my budget at $10, but you can set yours at whatever value you like. Go to https://cloud.google.com/translate/v2/pricing to view pricing details for using the Translate API. As of this writing, it costs $20 per 1 million characters of text. For reference, each time I translate Wearable Lanterns, it costs me about 20 cents. I would have to translate Wearable Lanterns 45 times to exceed my quota. Given that MCM translation is the absolute last thing I do before releasing an update, and only if the MCM changed, it would take a while before I exceeded this quota.
11. Run the script.  

    `python MCMTranslate.py mymod_english.txt`    

Your translation files will be output to the same directory as MCMTranslate.