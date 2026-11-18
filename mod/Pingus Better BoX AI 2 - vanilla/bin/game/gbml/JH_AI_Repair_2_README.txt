JH AI Repair 2 + Career Starts (layer for JH_PR_2.5 Jungle Hawks - WT 21 / WT 22)

INSTALL
Enable in JSGME AFTER the WT build (and after the Aces cockpit layer). Disable it first when the WT build changes.
Built by D:\Steam\Il2Mods1946\scripts\jh_ai_repair2\build_layer.py from the WT build named in its report
(work\jh_ai_repair2\report.txt). If WT 22 changes squadrons.cfg or career templates, rebuild with --base WT 22.

AI (bin\game\gbml\bbai.dll, bbai.ini)
Fault in the 18 Nov 02:14-03:18 log: after every DISENGAGE the flight went REGROUP -> ALERT -> ENGAGE inside 2 s
(a bandit pointing at the flight within 1.5 km counted as "attacked"), and the pair logic kept sending wingmen to
cover a shooter still in the fight. No flight re-formed for the trip home.
Change: after a disengage the flight holds REGROUP (the cruise formation on the lead's route) for egress_s = 150 s.
In that time: no brain attack order, no contact climb toward the enemy, no WT19 sun/setup route, no cover jobs or
hand-offs. An enemy on one of the flight inside 1000 m (nose within 30 deg) allows a fight of at most 60 s, then
the flight disengages again. Wingmen more than 1.2 km from the lead get the rejoin again every 20 s (not while an
enemy is on them). Out of ammo: no new fight for the rest of the mission. Self-defence always passes the gate.
Log line: "flight: JH AI Repair 2 egress" in gbml\bbai_log.txt. Keys: [Flight] egress_* / rejoin_every_s / straggler_km.

CAREER (data\scg\15, data\scg\22)
Air-start templates (templates\<id>\15000\0): WP3_IN 6 km before the objective on the line to home, the air start
8 km further back = 14 km from the objective. Before: 11 km behind a WP3_IN placed anywhere between base and target
(18 Nov top cover: 150 km). Mission types whose objective can be the home field (1105, 1153, relocations) and
escort rendezvous starts keep the stock rule. The briefing map still draws the server's WP3_IN.
Fighter squadrons: 1101 / 1103 intercepts capped at 100 km; an 1105 airfield-defence scramble added to periods
without one (where the career has an 1105 template); longer missions weighted down so 1101 / 1103 / 1105 are half
of each period's weight.

Not flown.
