# Austrian Check-in Simulator V11

Completely rebuilt from scratch as a stable standalone check-in simulation.

- all check-in data and logic live inside `index.html`
- select an active flight
- queue only shows passengers from that flight
- document verification
- no automatic seat on passenger opening
- automatic seat only when pressing **Sitz automatisch**
- rows 1–4 Business zone
- Business auto-seat uses rows 1–4
- Economy auto-seat uses rows 5+
- Economy may manually select rows 1–4 for €12
- internal seat map and passenger-display seat map
- random baggage weight
- baggage fee / rejection logic
- check-in complete removes passenger from the open queue
- second display: standard, flight, journey, seat map, baggage, success and advertising
- pause mode keeps ads and shows a closed-counter strip
