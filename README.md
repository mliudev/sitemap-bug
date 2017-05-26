# djangocms-blog sitemap bug demo

A prototype django cms project which demonstrates an internal server error bug
when visiting the sitemap.xml page. This bug occurs if there are no published
articles for a blog app config.

To demonstrate the bug first install the project requirements:

`pip install -r requirements.txt`

Run the server with:

`python manage.py runserver`

Navigate to the site:

`localhost:8000`

Navigate to sitemap.xml:

`localhost:8000/sitemap.xml`

You should see an internal server error indicating that one of the blog
app config namespaces throws a `NoReverseMatch()` error.

You can access the admin with:

Username: demo
Password: password1

Navigate to the 'Blog Articles' admin page and you'll see two articles
associated with two different app configs. Create a new page and attach 
the 'Blog' apphook with the 'Blog / Blog' app config. Publish the page.

Now navigate back to `localhost:8000/sitemap.xml` and you should see the page
load successfully.
