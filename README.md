# Event Scanner

A one-page QR check-in scanner for events. Each guest gets a unique QR code. Staff scan it at the door, the guest's name appears on screen, and the check-in is saved to a Google Form linked to a Google Sheet. Attendance is then exported to Excel.

Live scanner: https://dofus08.github.io/Event-Scanner/

## How it works

1. Guests are listed in a Google Sheet with an event name, guest ID, name and email.
2. One QR code is generated per guest. The code opens this page with the guest's details:
   `https://dofus08.github.io/Event-Scanner/?e=EVENT&id=GUEST_ID&n=NAME&m=EMAIL`
3. The page sends the check-in to a Google Form. Each check-in becomes a row in the linked Sheet.
4. After the event, the responses are exported to Excel: one sheet for attendees and one for no-shows. Only the first scan per guest counts.

## Using it at the door

There are two ways to scan:

- **iPhone Camera:** point the Camera app at the guest's QR code and tap the link.
- **Scanner page:** open the live scanner, tap Start scanning, and allow camera access. The camera stays inside the page, so staff can scan guest after guest without leaving it.

What staff see:

- **Green:** checked in, with the guest's name and email.
- **Repeat scan warning:** the guest was already scanned in this session.
- **Error:** the code isn't a valid guest QR, or the check-in didn't save. Tap retry.

Guests without their QR can be checked in by hand with **Manual check-in**.

## Files

- `index.html`: the whole scanner. It is a single static page with no server or database. It uses the html5-qrcode library for camera scanning.

## Updating the page

Replace `index.html` in this repo. GitHub Pages republishes it within a minute or two. The address is case-sensitive, so keep the capital E and S in `Event-Scanner`.

## Privacy

This repo holds no guest data. Names and emails live only in the QR codes and in the organiser's Google Sheet. The system collects only what attendance needs: name and email. Keep it that way under the PDPA.

## Maintainer

Mark Lim
