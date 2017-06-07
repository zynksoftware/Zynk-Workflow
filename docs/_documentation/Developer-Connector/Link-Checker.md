---
slug: link-checker
redirect_from: "/article/201-link-checker"
title: Link Checker
---
This task will check whether all of the hyper links on a web page are valid.

## Settings
### Depth
_Required_  
The maximum depth of sub-pages to check. Set to 1 to only check links on the URL specified, 2 to check links on each page linked to from the URL specified, etc.

### Output File
_Required_  
The XML file to save the results to.

### Timeout
_Required_  
The timeout for to use when fetching each page.

### Url
_Required_  
The URL of the web page to check.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [Developer Connector](developer-connector) article.

A sample output file is shown below. This output was produced whith the Url set to '[http://www.google.co.uk/](http://www.google.co.uk/)', and Depth set to 1.

```xml
<?xml version="1.0"?>
<CheckLinkResult>
	<Url>http://www.google.co.uk/</Url>
	<DateChecked>2015-02-25T17:00:28.3607396+00:00</DateChecked>
	<Links>
		<Link>
			<Links />
			<Title>Search</Title>
			<Href>https://www.google.co.uk/webhp?tab=ww</Href>
			<Result>OK</Result>
		</Link>
		<Link>
			<Links />
			<Title>Images</Title>
			<Href>http://www.google.co.uk/imghp?hl=en&tab=wi</Href>
			<Result>OK</Result>
		</Link>
		<Link>
			<Links />
			<Title>Maps</Title>
			<Href>http://maps.google.co.uk/maps?hl=en&tab=wl</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>Play</Title>
			<Href>https://play.google.com/?hl=en&tab=w8</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>YouTube</Title>
			<Href>http://www.youtube.com/?gl=GB&tab=w1</Href>
			<Result>MovedPermanently</Result>
		</Link>
		<Link>
			<Links />
			<Title>News</Title>
			<Href>http://news.google.co.uk/nwshp?hl=en&tab=wn</Href>
			<Result>OK</Result>
		</Link>
		<Link>
			<Links />
			<Title>Gmail</Title>
			<Href>https://mail.google.com/mail/?tab=wm</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>Drive</Title>
			<Href>https://drive.google.com/?tab=wo</Href>
			<Result>OK</Result>
		</Link>
		<Link>
			<Links />
			<Title>More</Title>
			<Href>http://www.google.co.uk/intl/en/options/</Href>
			<Result>MovedPermanently</Result>
		</Link>
		<Link>
			<Links />
			<Title>Calendar</Title>
			<Href>https://www.google.com/calendar?tab=wc</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>Translate</Title>
			<Href>http://translate.google.co.uk/?hl=en&tab=wT</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>Books</Title>
			<Href>https://books.google.co.uk/bkshp?hl=en&tab=wp</Href>
			<Result>OK</Result>
		</Link>
		<Link>
			<Links />
			<Title>Shopping</Title>
			<Href>http://www.google.co.uk/shopping?hl=en&tab=wf</Href>
			<Result>OK</Result>
		</Link>
		<Link>
			<Links />
			<Title>Blogger</Title>
			<Href>http://www.blogger.com/?tab=wj</Href>
			<Result>MethodNotAllowed</Result>
		</Link>
		<Link>
			<Links />
			<Title>Finance</Title>
			<Href>http://www.google.co.uk/finance?tab=we</Href>
			<Result>OK</Result>
		</Link>
		<Link>
			<Links />
			<Title>Photos</Title>
			<Href>https://plus.google.com/photos?tab=wq</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>Videos</Title>
			<Href>http://video.google.co.uk/?hl=en&tab=wv</Href>
			<Result>MovedPermanently</Result>
		</Link>
		<Link>
			<Links />
			<Title>Docs</Title>
			<Href>https://docs.google.com/document/?usp=docs_alc</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>Even more &raquo;</Title>
			<Href>http://www.google.co.uk/intl/en/options/</Href>
			<Result>MovedPermanently</Result>
		</Link>
		<Link>
			<Links />
			<Title>Sign in</Title>
			<Href>https://accounts.google.com/ServiceLogin?hl=en&continue=http://www.google.co.uk/</Href>
			<Result>OK</Result>
		</Link>
		<Link>
			<Links />
			<Title />
			<Href>http://www.google.co.uk/preferences?hl=en</Href>
			<Result>OK</Result>
		</Link>
		<Link>
			<Links />
			<Title>Search settings</Title>
			<Href>/preferences?hl=en</Href>
			<Result>BadRequest</Result>
		</Link>
		<Link>
			<Links />
			<Title>Web History</Title>
			<Href>http://www.google.co.uk/history/optout?hl=en</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>Install Google Chrome</Title>
			<Href>/chrome/index.html?hl=en&amp;brand=CHNG&amp;utm_source=en-hpp&amp;utm_medium=hpp&amp;utm_campaign=en</Href>
			<Result>BadRequest</Result>
		</Link>
		<Link>
			<Links />
			<Title>Advanced search</Title>
			<Href>/advanced_search?hl=en-GB&amp;authuser=0</Href>
			<Result>BadRequest</Result>
		</Link>
		<Link>
			<Links />
			<Title>Language tools</Title>
			<Href>/language_tools?hl=en-GB&amp;authuser=0</Href>
			<Result>BadRequest</Result>
		</Link>
		<Link>
			<Links />
			<Title>Advertising&nbsp;Programmes</Title>
			<Href>/intl/en/ads/</Href>
			<Result>BadRequest</Result>
		</Link>
		<Link>
			<Links />
			<Title>Business Solutions</Title>
			<Href>/services/</Href>
			<Result>BadRequest</Result>
		</Link>
		<Link>
			<Links />
			<Title>+Google</Title>
			<Href>https://plus.google.com/103583604759580854844</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>About Google</Title>
			<Href>/intl/en/about.html</Href>
			<Result>BadRequest</Result>
		</Link>
		<Link>
			<Links />
			<Title>Google.com</Title>
			<Href>http://www.google.co.uk/setprefdomain?prefdom=US&amp;sig=0_3zSQTaprT35oeaGdbeB8K-WpvDM%3D</Href>
			<Result>Found</Result>
		</Link>
		<Link>
			<Links />
			<Title>Privacy</Title>
			<Href>/intl/en/policies/privacy/</Href>
			<Result>BadRequest</Result>
		</Link>
		<Link>
			<Links />
			<Title>Terms</Title>
			<Href>/intl/en/policies/terms/</Href>
			<Result>BadRequest</Result>
		</Link>
	</Links>
</CheckLinkResult>
```