# MCM Translate
A utility for machine translating English SkyUI MCM Translation files into all other supported languages using Google Translate.

This utility translates an English SkyUI MCM translation file into the following languages:
* Czech
* French
* German
* Italian
* Japanese
* Polish
* Russian
* Spanish

###Warning
Using the Google Translate API **costs money**. How much it costs is dependent on how much text in your MCM files needs to be translated. However, I've found that using it saves so much time when releasing my projects that the cost is negligible. Be aware of the costs associated with using the Google Translate API and **set up a budget** in the Google Developer Console. If this all sounds scary, it's probably best that you not proceed.

###Usage

    python MCMTranslate.py [English MCM translation file] | [--help]

    [English MCM translation file]: UTF-16 LE with BOM encoded MCM translation file ending in 'english.txt'
    --help: Shows this help message.

###Instructions
1. Clone this repository.
2. Install Python 2.7 or newer.
3. Install `pip`, if necessary. https://pip.pypa.io/en/stable/installing/
4. Install the Google Translate API Client Library for Python.    

    `pip install --upgrade google-api-python-client`

5. Set up a Google Developer Console project named 'mod translate', or whatever you like. https://console.developers.google.com. Within the project, create a new application. Name it whatever you like.
6. In the Google Developer Console slide-out menu, go to *API Manager > Translate API*, and select *Enable*.
7. In the sidebar, select *Credentials*, and select *Create credentials > API key*. Create a 'server key'.
8. Create a file named `google_api_secret.txt` in the same directory as MCMTranslate.py. Copy and paste the generated API key into the text file. **Do not share this key with anyone, as it handles billing and quotas. You have been warned.**
9. In the Google Developer Console slide-out menu, go to *Billing* and create a billing account.
10. **IMPORTANT:** In the sidebar, go to *Budgets and Alerts* and create a budget for the project. This prevents you from accidentally spending more money when using the application than you intended. I set my budget at $10, but you can set yours at whatever value you like. Go to https://cloud.google.com/translate/v2/pricing to view pricing details for using the Translate API. As of this writing, it costs $20 per 1 million characters of text.
11. Run the script.  

    `python MCMTranslate.py mymod_english.txt`

Your translation files will be output to the same directory as MCMTranslate.

###Notes
Google has a separate quota, which is "characters per 100 seconds". It defaults to 10,000. If you run this utility back-to-back quickly, you can easily outstrip this quota with large MCM translation files.

This utility has a lot of room for improvement, but it suits my personal needs. This utility could be improved by: handling network communication errors, allowing the user to translate one language at a time using a command line flag, and so on. Feel free to create a branch and make enhancements.

Each time I translate Wearable Lanterns using MCMTranslate, it costs me about $1.04 (or, 13 cents per language). I would have to translate Wearable Lanterns 9 times to meet my budget. Given that MCM translation is the absolute last thing I do before releasing an update, and only if the MCM changed, it would take a while before I exceeded this quota.

###Disclaimer
MIT License

Copyright (c) 2016 Chesko

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.