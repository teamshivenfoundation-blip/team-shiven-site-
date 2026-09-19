# Team Shiven Foundation website

## Folder layout
- index.html: the whole site
- images/gallery: event and community photos
- images/team: headshots (optional, initials show until you add one)

## Add gallery photos
1. Rename each photo to something simple, lowercase, no spaces: bake-sale-2024.jpg
2. Put it in images/gallery
3. Open index.html, find `const GALLERY = [` and add a line:
   { src: "images/gallery/bake-sale-2024.jpg", caption: "Bake sale, 2024" },
4. Keep photos under about 500 KB each (compress at squoosh.app) so the site stays fast.

## Add team headshots
Save as images/team/firstname-lastname.jpg, all lowercase. Example: images/team/vahin-shah.jpg
Square photos look best.

## Update a stat or milestone
Search index.html for the number (27,493) or the year and edit the text.
Push the change to GitHub and Vercel redeploys automatically in about 30 seconds.

## Do not change
The <title> and <meta name="description"> lines at the top. Google shows them in search results.

## Turn on the AI helper ("Ask about Team Shiven")
The chat button runs on Claude through the file api/ask.js. It needs an API key:
1. Go to console.anthropic.com, create an account, add billing, and create an API key.
2. In Console > Settings > Limits, set a low monthly spend limit (for example $10). This caps your cost no matter how many people use it.
3. In Vercel: Project > Settings > Environment Variables. Name: ANTHROPIC_API_KEY. Value: your key. Save, then redeploy.
Never paste the key into index.html or anywhere on GitHub.
To change what the helper knows, edit the FACTS section in api/ask.js.
Until the key is set, the chat politely points visitors to the team email.

## Shiven's portrait
The photo in "Shiven's legacy" lives at images/shiven/shiven.jpg. To swap it, replace that file with another square photo using the same name.

## Upcoming events
Events live in the "EVENTS" section of index.html. Each event is one <li class="event"> line with data-date="YYYY-MM-DD".
Events disappear automatically the day after they happen. When every event has passed, the whole section and its menu link hide themselves.
Also update the event list in api/ask.js so the AI helper knows about new events.

## The video hero (top of the page)
- Background video and poster: the <video class="sh-art"> tag right under <!-- HERO --> in index.html. Swap the src and poster links to change footage.
- Words: edit the spans inside the hero. Keep each headline line short so it stays two lines on desktop.
- Colours and readability: the .sh-hero tokens at the top of the hero CSS. If the headline ever looks hard to read over the video, raise --sh-veil-center (desktop) or --sh-veil-center-phone.
- The fundraising total appears in the hero facts too. Search for 30,846 when it changes.
