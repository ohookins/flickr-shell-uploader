SUMMARY
=======

This is an extremely simple and naive photo uploader for Flickr.

REQUIREMENTS
============
 * curl
 * awk
 * grep
 * tr
 * md5sum (or md5)

USAGE
=====
flickr-shell-uploader [-t TITLE] [-d DESCRIPTION] [-a TAGS] [-p IS_PUBLIC] [-f IS_FRIEND] [-m IS_FAMILY] [-s SAFETY_LEVEL] [-c CONTENT_TYPE] [-h HIDDEN] -i <file> [-i <file> ...]

    All of the below options are optional (aside from files to upload):
    TITLE: Title of your photo.
    DESCRIPTION: Description of your photo.
    TAGS: Comma-separated list of tags for the photo (no spaces).
    IS_PUBLIC: 0 = no, 1 = yes - viewable by anyone.
    IS_FRIEND: 0 = no, 1 = yes - friends can view the photo.
    IS_FAMILY: 0 = no, 1 = yes - family can view the photo.
    SAFETY_LEVEL: 1 = safe, 2 = moderate, 3 = restricted.
    CONTENT_TYPE: 1 = photo, 2 = screenshot, 3 = other.
    HIDDEN: 1 = visible, 2 = hidden. Hides the photo from public searches.

    One or more files may be supplied, but the above options may only be useful for individual files!

It will create a "frob" which will need to be authenticated against your
account. When it asks you to, please visit the URL it prints out which will
take you to a page on Flickr where you can authenticate the request.

Once authenticated, a token is granted to this script that will be used from
then on to upload to your account. The frob and token are stored in
~/.flickr-shell-uploader. If you have removed access for this application
you should delete this file and start the authentication process again.

NOTES
=====
Proxies should be handled by curl natively.
