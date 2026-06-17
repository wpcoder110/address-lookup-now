=== Address Lookup Now ===
Contributors: ahmerhassan110
Tags: address search, autocomplete, service locator, address finder, redirect
Requires at least: 5.0
Tested up to: 7.0
Requires PHP: 7.4
Stable tag: 1.7.0
License: Commercial
License URI: https://addresslookupnow.com

Search addresses with autocomplete suggestions and redirect users to service pages. Track every search with weekly email reports.

== Description ==

Address Lookup Now is a WordPress plugin that provides an address search widget with live autocomplete suggestions. When a user selects a matching address they are redirected to the corresponding service page. If no match is found they are routed to a configurable fallback page or contact form.

**Key Features:**

* Live autocomplete suggestions as the user types
* Fuzzy matching across address, city, state, zip fields
* Redirect to service page on match
* Configurable fallback page or URL when no match is found
* Optional Zip Code field — auto-fills on match, required on no-match
* Local database sync — addresses stored in a local WordPress table for fast, scalable search (supports 20,000+ addresses)
* Google Sheets support — import address database from a published Google Sheet
* CSV File support — upload directly through the WordPress media library
* CSV URL support — link to a remotely hosted CSV file
* Configurable column mapping for Address, City, State, Zip, Service URL
* Visual appearance editor — configure colors, padding, font size, and border radius without writing CSS
* Live preview of the search form directly in the admin panel
* Search tracking dashboard with 24-hour, 7-day, and 30-day filters
* Weekly CSV email report sent automatically on a configurable day
* Manual test report button

== Installation ==

1. Purchase a license at https://addresslookupnow.com
2. Download the plugin ZIP from your account
3. Go to WordPress Admin → Plugins → Add New → Upload Plugin
4. Upload the ZIP and click Install Now, then Activate
5. Go to Address Finder → License and enter your license key
6. Click Activate — the full menu and all features will unlock
7. Go to Address Finder → Settings and configure your data source

== Configuration ==

= Data Source Tab =

Configure where your address data comes from. After saving, the plugin automatically fetches the data and imports it into a local WordPress database table. All searches run against this local table for maximum speed — no live API calls on every keystroke.

Click **Save & Sync Addresses** any time your Google Sheet or CSV has been updated to re-import the latest data.

= Data Source: Google Sheets =

Paste your Google Sheet URL into the Google Sheet URL field. The sheet must be shared publicly (anyone with the link can view). Required columns: Address, City, State, Zip, Service URL.

= Data Source: CSV File =

Upload a CSV file directly through the settings page. The file is stored in your WordPress media library.

= Data Source: CSV URL =

Provide a publicly accessible URL pointing to a CSV file. The plugin fetches it on sync.

= Column Mapping =

If your column headers differ from the defaults, update the column name fields to match your sheet or CSV exactly. Column names are case-sensitive.

= General Settings Tab =

Configure search tracking, weekly email reports, and the fallback destination for unmatched addresses.

= Fallback Behavior =

When no address match is found, users are routed to the fallback destination. Configure either a WordPress page or a custom URL.

= Appearance Tab =

Customize the look of the search form without writing any CSS. Adjust accent color, button text color, input background, input text color, font size, border radius, vertical padding, and horizontal padding. Changes are previewed live in the admin panel before saving. Enable or disable the Zip Code field from this tab — the preview updates instantly to show the result.

== Shortcode ==

Place the search form anywhere on your site:

    [address_search]

Optional attributes:

    [address_search placeholder="Type your address..." button_text="Find My Service"]

== Search Tracking ==

Go to Address Finder → Search Tracking to view all recorded searches. Filter by Last 24 Hours, Last 7 Days, or Last 30 Days. Each row shows the date/time, search query, zip code, result (Found/Not Found), and matched address.

A CSV report is emailed automatically every week on the configured day. Configure the recipient email and report day in General Settings. Multiple recipients are supported — separate email addresses with commas.

Use the Send Test Report button to send an immediate report without waiting for the scheduled send.

Use Clear All History to permanently delete all search records. This cannot be undone.

== Frequently Asked Questions ==

= The shortcode shows nothing =

Ensure the plugin has an active license. Check that the data source is configured and that at least one sync has been completed in the Data Source tab.

= Autocomplete is not working =

Check the browser console for JavaScript errors. Ensure your data source is configured correctly and that you have clicked Save & Sync Addresses at least once. Check that column names in Settings match your sheet or CSV exactly.

= Search is slow before syncing =

Before the first sync the plugin falls back to fetching data live from your sheet or CSV on every search. Click Save & Sync Addresses in the Data Source tab to import addresses into the local database and enable fast search.

= The weekly report is not sending =

Ensure WordPress Cron is running — some hosts require a real cron job to trigger wp-cron.php. Verify the report email address is correct in General Settings. Use the Send Test Report button to confirm email delivery is working.

== Changelog ==

= 1.7.0 =
* Significantly improved address search speed and responsiveness
* Fixed an issue causing search errors on some sites with caching enabled
* Smoother autocomplete experience with faster, more accurate suggestions while typing
* Prevented duplicate or premature form submissions while a search is processing
* Hardened the address field against browser autofill interference
* Fixed autocomplete suggestions appearing in the wrong position on mobile devices
* Fixed the Zip Code "Required" warning overlapping the search button on mobile

= 1.6.0 =
* Added local database sync — addresses imported into wp_af_addresses table for fast search (supports 20,000+ addresses)
* Save & Sync fetches data, truncates and re-imports in a single transaction for reliability
* Added Appearance tab — visual editor for colors, padding, font size, border radius with live preview
* Live preview of search form in admin panel, updates instantly on every change
* Zip Code field toggle moved to Appearance tab — visible in live preview
* Settings page reorganised into three tabs: Data Source, General Settings, Appearance
* Added button_text shortcode attribute
* Added 24-hour filter to Search Tracking page

= 1.5.0 =
* Minor bug fixes and stability improvements

= 1.4.1 =
* Minor bug fix

= 1.4.0 =
* Bug fixes

= 1.3.0 =
* Added EDD Software Licensing integration
* Added hourly license status check
* Added license activation/deactivation page
* Improved menu structure — gated behind license status

= 1.2.0 =
* Added Zip Code / Community field
* Added auto-fill behavior on address match
* Added zip capture in search tracking and weekly reports

= 1.1.0 =
* Added Community/Town field toggle
* Added live-site database migration via maybe_upgrade_table()

= 1.0.0 =
* Initial release
* Address autocomplete search form
* Google Sheets and CSV data source support
* Service page redirect on match
* Fallback page on no match
* Search tracking database table
* Weekly CSV email report

== Upgrade Notice ==

= 1.6.0 =
After updating, go to Address Finder → Settings → Data Source and click Save & Sync Addresses to import your addresses into the local database.
