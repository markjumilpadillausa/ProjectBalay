# ProjectBalay

Our family house, one phase at a time. A Family Project. Created October 24, 2026. Version 1.2.0, updated November 2, 2026.

## What the public sees
The 3D house, the moving sun, and how much sun each room gets. Nothing else.

## What only Mark and Yda Jane see (PIN)
Materials per phase with Supplier 1, 2 and 3 prices, the supplier comparison, the budget with the 70/30 computation, and the savings and spending log.

## New in version 1.2.0
**Site compass (public).** On the House tab, press Start phone compass, stand where the middle of the house will be and hold the phone flat. The plan turns with the phone and tells you which wall and which rooms are in front, behind, left and right. Use "Line up a string" to find the direction for the long walls or the end walls. Needs https (GitHub Pages is fine). On iPhone, allow motion and orientation when asked. Try it flat like the compass app, and keep it away from metal.

**3D view.** Drag to turn, pinch to zoom, drag with two fingers to move it, twist two fingers to rotate. With a mouse: Shift or right button and drag to move. Double tap to reset.

**Price sheet for the stores.** Materials tab, Print price sheet. One A4 page for each list, only the item, description, quantity, unit and an empty box for the price. It shows no name, no email and no estimate. The only contact is 09760014007. When printing, turn off "Headers and footers" in the print window.

**Encode prices.** Materials tab, Encode prices. Choose the store (Supplier 1, 2 or 3) and the list number, add a photo of the filled sheet, then type each price in the big boxes. Tap NA when the store wrote NA. Enter moves to the next item. The comparison updates at once. The app does not read handwriting by itself.

**Paste a list.** Materials tab, Paste a list. Paste the carpenter's list, one item on each line: Item | Quantity | Unit | Details.

## Files in this folder
index.html, sw.js, manifest.json, icon-192.png, icon-512.png go to GitHub. Code.gs goes to Google Apps Script.

## Setup

1. Create a Google Sheet with your own Google account. Name it "ProjectBalay".
2. In the Sheet: Extensions, then Apps Script.
3. Replace everything in Code.gs with the Code.gs from this folder. Save.
4. In the editor choose **setup** (not doGet) and press Run. Allow the permissions. This builds the KV and Log sheets, loads the starting material list and sets both PINs to 102026.
5. Deploy, New deployment, type Web app. Execute as: Me. Who has access: Anyone. Deploy and copy the Web app URL.
6. On GitHub, create a repository named ProjectBalay. Upload index.html, sw.js, manifest.json, icon-192.png and icon-512.png.
7. The Web app URL is already built into index.html, so there is nothing to paste. Only if you ever make a brand new deployment, open index.html on GitHub, find `var API_URL` and paste the new URL between the quotes.
8. Settings, Pages, Deploy from branch main, root. Your link will be markjumilpadillausa.github.io/ProjectBalay
9. Open the link. Press Sign in. Choose your name, type 102026. The app asks you to choose your own PIN.
10. Open the link once on each phone while the internet is on. After that it also opens with no signal.

## After a code change
Apps Script: Deploy, Manage deployments, pencil, New version, Deploy. Always use New version on the same deployment so the URL stays the same. GitHub: upload the new index.html. The URL is already inside it.

## If a PIN is forgotten
Mark can reset Yda Jane's PIN in the app (More, Reset Yda Jane's PIN). If Mark forgets his, run **resetPins** in Apps Script. Both PINs go back to 102026.

## How offline works
Open the app while online once and your list is saved on that device. With no signal you can still type prices, add items and log money. Each change waits in a queue, shown as "N waiting". When the internet returns, it sends by itself. If two phones change the same item, the newest change wins.

## Good to know
Prices and money are checked on the server by PIN. The page on GitHub holds no prices. The starting prices in Code.gs are sample estimates, not real quotes, so replace them with the hardware quotes. A phone that is signed in keeps its own copy of the data. Use "Sign out and clear this device" on a phone that is not yours.
