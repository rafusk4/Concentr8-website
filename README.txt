CONCENTR8 — concentr8.eu
========================

This folder IS the website. Upload its contents to any static host.

  index.html            the page
  img/                  cans, photography, logo files
  favicon.svg           browser tab icon
  apple-touch-icon.png  iOS home-screen icon
  favicon-32.png        fallback icon for older browsers
  robots.txt            lets search engines index the site
  sitemap.xml           one entry, the homepage

DEPLOY (Cloudflare Pages, free, recommended)
--------------------------------------------
1. dash.cloudflare.com -> Workers & Pages -> Create -> Pages
   -> "Upload assets". Drag this whole folder in. Deploy.
2. In that project: Custom domains -> Set up a domain
   -> type concentr8.eu
3. Cloudflare tells you which nameservers to use. Go to the registrar
   where you bought concentr8.eu and replace its nameservers with those.
4. Wait for DNS to move over (usually under an hour, up to 24h).
   HTTPS is issued automatically.

Netlify and Vercel work the same way: drag the folder in, add the
custom domain, then point DNS at them.

TO UPDATE LATER
---------------
Edit index.html (or swap a file in img/) and upload the folder again.

THE CONTACT FORM
----------------
Right now the form writes the email and the visitor sends it from
their own mail app. Nothing is submitted to a server, so nothing can
be lost, but nothing lands in an inbox by itself either.

To make submissions arrive at concentr8.team@gmail.com:

  Netlify  - host there, then add to the <form> tag:
             name="contact" data-netlify="true"
             and add  <input type="hidden" name="form-name" value="contact">
             as the first child of the form.
             Netlify -> Forms -> Notifications -> email to your address.

  Any host - create a form at formspree.io, then set
             action="https://formspree.io/f/XXXXXXX" method="POST"
             on the <form> tag and delete the submit handler at the
             bottom of index.html.

Either way, test it once after going live.

NOTE ON IMAGE RESOLUTION
------------------------
Every image here is at the full resolution of the files supplied.
If higher-resolution originals of the can renders or the photography
exist, replace the matching file in img/ and the page sharpens with
no code change, as long as the new file keeps the same proportions.
