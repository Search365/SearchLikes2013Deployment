Assuming the base SharePoint 2013 is installed and central admin has been provisioned. The following steps will make searchlike available

1. Provision a web application
2. Provision a root site collection on the web application with teamsite as template
3. Provision a Enterprise search center (another site collection with managed path /sites/searchcenter) on the web application with template "Enterprise Search Center"
4. Provision Search Service with farm account as search service account and content access account (just lab server), and add the proxy to default proxy group. 
5. Set global Search Center URL to the url of the search center created at step 3. It will take a little while to let the service to push the settings to the web apps which associated to it
6. Copy jquery-1.11.1.min.js, jquery-ui-1.11.0.custom, jquery.SPServices-2013.01.min.js to root site collection root site Style library. 
7. Map a network drive to the SharePoint 2013 Master Page Gallery on the search center site collection (http://msdn.microsoft.com/en-us/library/jj733519.aspx)
8. Open the mapped drive in windows explorer, then drag and drop Control_Like_SearchResults.html and Item_Like_Default.html into search folder of the master page gallery. 
10. Go to site settings of search center site collection root site. Create a new query rule by click "Search Result Type" under site collectiona administration. Then go to "New Result Type". 
    Give a new "Search Like" or any other name, and pick "Like Default Item" in "What should these results look like" dropdown. 
11. Edit default.aspx in pages library on search center site collection root site, then edit search result web part. On the property panel, expand "Display template", and switch the Results 
    control template to "Like Default Result". 

12. Do a full crawl on the sharepoint content source. then done!