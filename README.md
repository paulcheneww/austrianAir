# Austrian Airlines – Vienna Check-in Simulator

Private browser-based simulation of an Austrian Airlines check-in counter at Vienna Airport.

## Included

- 24 Austrian flight records
- roughly 200 generated fictional passengers
- PNR, ticket number and passenger search
- Economy, Premium Economy and Business
- fare families including Light / Classic
- frequent-flyer statuses
- document verification
- passport and visa-check cases
- seat assignment with seat map
- checked baggage and baggage tags
- baggage allowance logic
- excess baggage / extra-piece simulation
- maximum 32 kg acceptance check
- upgrade offers
- special service requests (SSR)
- connections
- check-in closing status
- boarding pass simulation
- payments / fees
- shift statistics
- dedicated passenger-facing second display

## Second display

Open `passenger-display.html` using the button in the sidebar and move it to the second monitor.

The display can show:
- welcome screen
- passenger itinerary
- flight / gate / seat
- baggage weight and excess fee
- upgrade offer
- boarding pass summary

For the most reliable synchronization, run both pages on the same GitHub Pages site.

## GitHub Pages

Upload all files into the repository root and enable:

Settings → Pages → Deploy from a branch → main → /(root)

## Important

All passenger, booking and ticket data are fictional. The simulator is not connected to Austrian Airlines, Lufthansa Group, Vienna Airport, any real departure-control system, or live airline systems.


## Version 2 – flight-by-flight counter workflow

- select one active Austrian flight for the counter
- passenger queue is filtered to that flight
- process passengers one by one
- after successful check-in the passenger disappears from the open queue
- passenger display automatically returns to the active flight information
- manual display buttons:
  - standard / welcome screen
  - active flight information
  - passenger-specific journey
  - baggage weighing
  - upgrade offer
  - boarding pass
- pause mode:
  - clears active passenger
  - passenger display shows that the counter is temporarily unattended
  - ending the pause returns the display to the active flight
- switch to the next flight whenever the current flight is finished


## Version 3

- After every successful passenger check-in the second display automatically returns to the active flight screen.
- The active flight screen now shows:
  - flight number
  - destination
  - departure time
  - gate
  - aircraft
  - counter number
  - checked-in / total passenger count
  - passengers remaining
  - "Ready for next passenger"
- Baggage weight is automatically randomized whenever the baggage workflow is opened.
- Most generated bags are within allowance, some are overweight, and a small number exceed 32 kg.
- **Neu wiegen** generates a new random scale reading.


## Version 4 – richer Austrian passenger display

The passenger-facing display has been redesigned around Austrian's red visual identity.

New:
- full red Austrian-style active flight screen
- very large destination
- large flight number and route
- departure, gate, aircraft and counter
- white check-in status panel
- remaining passenger count
- "Ready for next passenger"
- rotating information screens between passenger interactions
- document reminder
- baggage-on-scale reminder
- seat / boarding-pass reminder
- standard screen also uses Austrian red
- passenger-specific baggage, upgrade and boarding-pass views remain available

The look is inspired by Austrian's public red-and-white brand identity, but the simulator is not an official Austrian Airlines product.


## Version 5

New counter and passenger-display behavior:

- active flight check-in can be manually closed and reopened
- closed flights are rejected by the normal check-in completion logic
- success animations appear for:
  - seat confirmation
  - baggage accepted
  - passenger check-in completed
- after each success animation the display returns automatically to the appropriate passenger or active-flight screen
- new advertising mode on the second display
- advertising rotates between simulated cards for:
  - Austrian Airlines
  - Lufthansa Group
  - Vienna Airport
  - Austrian Business Class
- pause mode now keeps the advertising running
- during pause, only a red top strip says:
  "Dieser Schalter ist momentan geschlossen · This counter is temporarily closed"
- display can be manually switched between:
  - standard
  - active flight information
  - advertising
- these promotional visuals are fictional simulator content and not official advertising assets


## Version 6 – seat workflow

- opening a passenger automatically assigns a random available seat if none exists
- the agent can click **Sitz automatisch** to assign another available seat
- **Sitzplan am Display** sends the cabin seat map to the passenger-facing monitor
- the passenger display shows available, occupied and currently selected seats
- the passenger can visually choose a seat; the agent then clicks the corresponding seat in the internal seat map
- confirming a seat still triggers the animated seat-confirmation screen


## Version 7 display rebuild

The passenger-facing monitor was rebuilt from scratch to eliminate conflicts from the earlier patched versions.

- visible `DISPLAY V7` marker to verify the browser loaded the new file
- cache-busted display URL (`passenger-display.html?v=7`)
- Austrian-red standard and active-flight screens
- separate full-screen modes for journey, seat map, baggage, success, upgrade and boarding pass
- seat map shows the proposed seat prominently and highlights it in the cabin
- success animations are no longer reset by the display polling timer
- advertising is a true full-screen mode and rotates every 6 seconds
- advertising includes image-based Austrian / Vienna / lounge cards plus Lufthansa Group
- pause keeps advertising visible and adds only the red closed-counter strip at the top


## Version 8

- document/passport verification now triggers a short success animation on the passenger display
- if the active passenger is Business Class, the passenger-facing visual theme switches from Austrian red to `#2B3087`
- Business theme applies to journey, success, seat-selection and related passenger-specific screens
- a BUSINESS badge is shown in the display branding for Business Class passengers
- after the passenger flow ends, the active-flight screen returns to the normal Austrian-red counter theme


## Version 10 – repaired build
V9 accidentally lost the main JavaScript block during generation. V10 is rebuilt from the working V8 base.

Seat rules:
- no automatic seat when opening a passenger
- **Sitz automatisch** assigns a seat only when pressed
- Business auto-seat: rows 2–5
- Economy auto-seat: row 6 onward
- rows 2–5 are visibly marked as Business zone
- Economy can manually choose rows 2–5 for €12
- the €12 fee appears in transactions
- internal and passenger-facing seat maps remain available
