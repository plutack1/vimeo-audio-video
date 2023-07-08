# Download segmented videos from Vimeo

## Install prerequisites

Install ffmpeg and Python 3:
* Debian/Ubuntu: `sudo apt install -y ffmpeg python3`
* Mac OS X: `brew install ffmpeg python`
Install Python dependencies: `sudo python3 -m pip install requests --upgrade tqdm`

* For windows: use chocolatey to install python3 and ffmpeg. tqdm module can be installed using cmd as admin after
  'cd <directory intended for download of videos with the content of this repo in it>'
Install Python dependencies: `python -m pip install requests --upgrade tqdm`


## Instructions to download video
For each video you want to download:
1. Open the page containing the embedded video.
2. Open development console (Chrome: F12).
3. Go to the Network tab.
4. Right click on the `master.json` request, select Copy → Copy link address. An example of how such a URL could look like: `https://178skyfiregce-a.akamaihd.net/exp=1474107106~acl=%2F142089577%2F%2A~hmac=0d9becc441fc5385462d53bf59cf019c0184690862f49b414e9a2f1c5bafbe0d/142089577/video/426274424,426274425,426274423,426274422/master.json?base64_init=1](https://96vod-adaptive.akamaized.net/exp=1688780566~acl=%2Fcbaa521a-e70d-44b2-833a-103d5dabde57%2F%2A~hmac=02545dd4fbc81a26cf678ce450ead2ab03b09b61bcce3dba1f96b547d160fd7c/cbaa521a-e70d-44b2-833a-103d5dabde57/sep/video/5e906100,9603d058,a8c4edda,ba13a32a,e572d4c7/audio/73cebdc7,a4225903,b7d48b13/master.json?base64_init=1&query_string_ranges=1)`. Further modification of the master.json url doesnt appaear to be necessary.
   

Create a TSV file (can be done e. g. by copy-pasting from Google Sheets), where the first column is output file name (ending with `.mp4`) and the second is this URL to `master.json`.

a sample file 'sample_download.tsv' is included in this repo which can be editted and/or renamed for easier use.

Then run the script, providing the name of this file with names and URLs:
```bash
./vimeo-autio-and-video.py -i download.tsv
```

## Acknowledgements
Based on work of:
* @alexeygrigorev: https://gist.github.com/alexeygrigorev/a1bc540925054b71e1a7268e50ad55cd
* @brasno: https://gist.github.com/brasno/25fe2d30a31b40fe98cc9f55cfb709ab
* @AbCthings: https://github.com/AbCthings/vimeo-audio-video
* @DraZen-es code modification [here](https://gist.github.com/alexeygrigorev/a1bc540925054b71e1a7268e50ad55cd?permalink_comment_id=4589981#gistcomment-4589981)
