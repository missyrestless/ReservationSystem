# Second Life Reservation System

A dialog menu based reservation system for Second Life

## INTRODUCTION

The Truth & Beauty Lab Reservation System provides an easy to use dialog menu interface allowing visitors to book a reservation date, time, and destination or event. The owner can set individual schedules and prices for each destination or event. The reservation is booked when the reservation board receives payment equal to or greater than the price for the event. Notice of the reservation is sent to the owner via Instant Message and, if configured, Email. The visitor also receives an Instant Message and dialog informing them that their reservation has been booked. The Reservation System owner can configure the destination/event names, prices, default price, email address, hover text, board texture, dialog menu text, days of week to display, and times of day to display. This document is available in PDF format at http://www.scribd.com/missyrestless

## CONTENTS

This package contains:
    * Three preconfigured reservation boards (airline, event, and escort)
    * The Reservation System Owners Manual
    * Sample configuration notecards for airline, event, and escort bookings
    * A landmark to the demonstration Reservation Board at Truth & Beauty Lab

## SETUP OVERVIEW

### Rez and Unpack the Box

Upon purchase you will receive a boxed Reservation System. Rez and unpack the box (right click the rezzed box and select �Open� then copy the contents to your inventory). Your inventory should now contain a folder �Reservation System�. In this folder you will find three Reservation Board objects, the owner manual, sample Config notecards, and landmark.

### Rez and Position the Reservation Board

Select a location for your Reservation Board and drag one of the Reservation Boards from your inventory to the ground. Position the rezzed Reservation Board by right clicking it, selecting �Edit� and using the position arrows.

### Grant Debit Permission

When first rezzed the Reservation Board will display a dialog window requesting debit permission from the owner. The board needs debit permission in order to refund payment amounts exceeding the price of an event, refund underpayments, or run in demonstration mode refunding all payments. No Lindens are ever debited from the owner's account that were not erroneously paid through the Reservation Board or paid in demonstration mode. Granting debit permission is recommended. However, the Reservation Board will still function properly if debit permission is denied. See the NOTE ON DEBIT PERMISSION below for a further discussion of debit permission.

### Add a Custom Texture to the Board's Contents

If you would like to customize the appearance of your reservation board, create and upload an image to use on your board. Perhaps a snapshot of your business, event, or service with whatever text you want to display on the board. I use the Gimp for this (a Photoshop like free image editing tool from gimp.org). Upload the custom image and drop it in the reservation board's contents. This step is not always necessary � you may be perfectly happy with one of the boards provided.

### Edit the Config Notecard

Edit the configuration notecard named Config in the object's contents. Details on editing the Reservation Board configuration notecard Config are provided below. The default configuration is to accept reservations for every day of the week and all 24 hours in each day. No email address is configured by default.

### Edit the Info Notecard

Edit the Info notecard adding descriptions of the available bookings and prices along with any other information you wish to provide clients who request info. A default Info notecard is provided and may be sufficient for your purposes. If you do not wish to deliver a notecard on request, simply delete or remove the Info notecard from the object.

## EDIT THE RESERVATION BOARD NOTECARD

The Config notecard can be edited to configure the default settings for:

    * Destination/event/service names
    * Price for each destination/event/service
    * Default price
    * Hover text to display
    * Texture to use on the board's front and back sides
    * Dialog menu text
    * Name of the reservation board
    * Type of activity bookings are offered for
    * Days of the week to accept reservation requests
    * Times of day to accept reservation requests
    * Email address to use when notifying the owner of a request
    * Demonstration mode

The Config variables and their default settings follow:

```
EVENT_TYPE = Destination
This value is used as the main button label and in dialog messages. Example values might be Destination, Event, Escort, Class, Seminar, Rental, ...

EVENTS = Kazenojin,Bretton,Kotora
Comma separated list of events, escorts, services, or destinations.
 
PRICES = 1000,750,1250
Comma separated list of airfares, service fees, or event admission prices. These must match exactly the order of destinations listed above. Prices are in L$

DEFAULT_PRICE = 1000
The price for events/destinations/services not listed (in L$)

HOVER_TEXT = 
The text to display hovering above the board. By default, no hover text is shown.

TEXTURE = custom-texture-name or uuid
To specify a custom texture set TEXTURE = the custom texture name or uuid. If specified by name the texture must be copied into the board's inventory.

MAIN_DIALOG = Main Menu - Select a Reservation Date, Time, and Destination
Text displayed at the top of the Main dialog menu

DATE_DIALOG = Date Menu - Select a Reservation Date
Text displayed at the top of the Date dialog menu

TIME_DIALOG = Time Menu - Select a Reservation Hour
Text displayed at the top of the Time dialog menu

DEST_DIALOG = Destination Menu - Select a Reservation Destination
Text displayed at the top of the Destination dialog menu

EMAIL = you@your.com
The email address to be used if email notification is desired.

NAME = Reservation Board
The name of the reservation board object, e.g. Fuji Airline Reservation Board

DAYS = Mon,Tue,Wed,Thu,Fri,Sat,Sun
The days of the week on which you wish to book reservations. The setting must be one or more of the exact three letter weekday name abbreviations above. For instance, to book reservations for Mondays, Wednesdays, and Fridays only set:
    DAYS = Mon,Wed,Fri
To set a per-event schedule, separate each events list of days with the pipe symbol (|). For instance, to schedule 3 events with 3 different sets of days:
    DAYS = Mon,Wed,Fri|Tue,Thu|Mon,Tue,Wed,Thu,Fri

TIMES = 8 AM,9 AM,10 AM,11 AM,12 PM,1 PM,2 PM,3 PM,4 PM,5 PM,6 PM,7 PM,8 PM,9 PM,10 PM,11 PM,12 AM,1 AM,2 AM,3 AM,4 AM,5 AM,6 AM,7 AM
The hours of the days specified above you wish to book reservations. These can be any string identifying a time of day, separated by commas. For instance, to book reservations at 9:30 AM, Noon, 3:45 PM, and Midnight only set:
    TIMES =  9:30 AM,Noon,3:45 PM,Midnight
To set per-event times of day, use a syntax similar to that described above for DAYS (separate each daily times list with the | symbol). For instance, to set individual event times of day for 3 events:
    TIMES = 8 AM,1 PM,4 PM|6 PM,9 PM,11 PM|10 AM,1 PM,4 PM,7 PM,10 PM 
All times are SLT (PST) which is GMT -8 with daylight savings calculated.

REFUND = FALSE
Set to TRUE to run a demo and refund any payments
```

## NOTE ON DEBIT PERMISSION

The first time the reservation board is rezzed it will prompt the owner for debit permission. This is required to enable the board to refund under and over payments or to act as a demonstration board. If you wish to enable these features then grant debit permission. Denying debit permission does not disable the board � it will still function. However, without debit permission under and over payments cannot be refunded. Note also that debit permission needs to be granted each time the board is re-rezzed or the scripts reset.

Truth & Beauty Lab recommends granting debit permission each time the board is rezzed or reset. Extreme care has been taken to verify that only under and over payments will be debited from the owner's account. In the case of an underpayment the client will be informed and no reservation is booked. In the case of an overpayment the client is informed, only the amount over the price is refunded, and the reservation is booked.

## FURTHER INFORMATION

The Truth & Beauty Lab Reservation System works well with the Truth & Beauty Lab Email2IM product at http://tinyurl.com/4h6gvqk Using the Email2IM object you can email a request confirmation directly back to the requester when you receive the email notification of the request. No need to log back into Second Life just to confirm the request. In fact, the Email2IM object's contents can be moved into the Reservation Board's contents so as to only use a single prim for both products.

This document, the Online Notification User Guide, the Pandorabot METAbolt Add-On Manual, the Pandorabot Actorbot Add-On Manual, Pandorabots Owner Manual, and Pandorabots User Guide are all available in PDF format at http://www.scribd.com/missyrestless

View and interact with the Truth & Beauty Lab demonstration Pandorabots at http://slurl.com/secondlife/Gualdo/204/224/43  http://slurl.com/secondlife/Gualdo/210/226/42/ and http://slurl.com/secondlife/Gualdo/204/224/43 (mature).

Email missyrestless@gmail.com with any questions, comments, suggestions, etc.

View other Truth & Beauty Lab creations in the Second Life Marketplace at http://tinyurl.com/2bq6o3p 
