hooulu.risehi.com — deploy notes
=================================

FILES
  index.html    the whole page. Fonts, logo and both headshots are inlined,
                so this file works on its own with no asset folder.
  og.jpg        1200x630 link preview image (email, iMessage, Slack, Facebook).
  favicon.png   512x512 browser tab icon.

All three go in the SAME directory at the root of the subdomain:
  hooulu.risehi.com/index.html
  hooulu.risehi.com/og.jpg
  hooulu.risehi.com/favicon.png

og.jpg and favicon.png are referenced by absolute URL
(https://hooulu.risehi.com/...), which link previews require. If the subdomain
ever changes, search index.html for "hooulu.risehi.com" and replace.

PAYMENT LINKS — all six are live
  Presenting   $20,000  ...3Ru07
  Kilohana     $10,000  ...3Ru09
  Kakoo         $5,000  ...3Ru0a
  Hoaloha       $2,500  ...3Ru0b
  Individual      $250  ...3Ru0c
  Aloha Supp.   $1,000  ...3Ru0d
  Every button opens Stripe in a new tab. No JavaScript on the page at all.

BEFORE YOU SHARE THE LINK — test each of the six
  Open every button and confirm the amount and product name on the Stripe page
  match the tier you clicked. Five minutes now beats refunding a $10,000
  mis-charge later.

STRIPE SETTINGS TO CHECK
  - Presenting Sponsor: set quantity limit to 1. Only one exists, and nothing
    on the page stops a second person buying it.
  - Individual seat: enable adjustable quantity so a buyer can take 2-3 seats
    in one checkout.
  - Set each link's confirmation page to a thank-you URL, and turn on receipt
    emails.
  - Collect billing name and address on every link so acknowledgment letters
    can be mailed.

ACKNOWLEDGMENT LETTERS ARE STILL MANUAL
  A Stripe receipt is not a 501(c)(3) acknowledgment. Every buyer needs a
  written letter stating the fair market value received:
     $1,440  presenting sponsorship (two tables, 16 guests)
       $720  per table of eight
        $90  per individual seat
  Deductible portion = amount paid minus that value.

HOSTING
  Static files. Netlify, Vercel, Cloudflare Pages or S3 all work by dropping
  the folder in, then pointing a CNAME for "hooulu" at the host.
  On Squarespace this needs a custom page or code block; the subdomain route
  is simpler.
