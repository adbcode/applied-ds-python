# Tips on Saving Coursera Workspace
For data science and Python programming courses, you often work in a Jupyter interface in Coursera. This makes it very convenient to learn, but a bit tricky when it comes to saving your work.

The default option is to open the notebooks/files you want to save and use *File* -> *Download as* option, which gets very manual when treating with a lot of files.

The best approach in my opinion is to open a Terminal window by using *New* -> *Terminal* in Jupyter and using the commands lined out in this [StackOverflow comment](https://stackoverflow.com/a/56318823).

More specifically, run `tar cvfz allfiles.tar.gz *` (replace *allfiles* with name of your preference) to archive everything. You can then download the file just like you would a regular notebook and open the file using 7zip.

In case the archive >100 MB (e.g. *Applied Plotting, Charting & Data Representation in Python* workspace), you should split the file using the second command in the above comment. You can split files in 100 MB chunks instead of 50 MB, and a bit higher if lucky.

Unfortunately, if the archive is many GBs in size, it makes it still a rather manual task to download several part files. The batch downloader addons in Firefox does not help as it was not configured to use cookies in Private browsing. Same goes for a script, unless you configure the downloader (whether *wget* in Linux or *requests.get* in Python) to use cookies from your current session.

Whichever the way you choose, you can create download links using the following format: `https://######################.labs.coursera.org/files/allfiles.tar.gz.part.XX?download=1`, where the #s replace a random string of alphabets and XX replace alphabets in increasing order (*aa, ab, ac, ...*).

The lab interface is very prone to slowdown and unresponsiveness when the compression occurs or when trying to download a big file. Just be patient and it helps to queue up mutliple files for download simultaneously.

If you are technically sound, it might help to use a utility instead, such as [coursera-dl](https://github.com/coursera-dl/coursera-dl).