-----
Scope
-----

This library does NOT help you publish a podcast, or manage the metadata of your
podcasts. It's just a tool that accepts information about your podcast and
outputs an RSS feed which you can then publish however you want.

Both the process of getting information
about your podcast, and publishing it needs to be done by you. Even then,
it will save you from hammering your head over confusing and undocumented APIs
and conflicting views on how different RSS elements should be used. It also
saves you from reading the RSS specification, the RSS Best Practices and the
documentation for iTunes' Podcast Connect.

Here is an example of how PodGen fits into your code:

1. A request comes to your webserver (using e.g. `Flask <https://palletsprojects.com/p/flask/>`__)
2. A podcast router starts to handle the request.
3. The database is queried for information about the requested podcast.
4. **The data retrieved from the database is "translated" into the language of PodGen, using its Podcast, Episode, People and Media classes.**
5. **The RSS document is generated by PodGen and saved to a variable.**
6. The generated RSS document is made into a response and sent to the client.

PodGen is geared towards developers who aren't super familiar with
RSS and XML. If you know exactly how you want the XML to look, then you're
better off using a template engine like Jinja2 (even if friends don't let
friends touch XML bare-handed) or an XML processor like the built-in
`Python ElementTree API <https://docs.python.org/3/library/xml.etree.elementtree.html#module-xml.etree.ElementTree>`__.
If you just want an easy way to create and manage your podcasts,
check out systems like `Podcast Generator <http://www.podcastgenerator.net/>`_.
