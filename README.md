WattBalance
===========

A Watt-balance, inspired by NIST's LEGO Watt Balance

Reference:

* arXiv:1412.1699 [physics.ins-det]
*A LEGO Watt Balance: An apparatus to demonstrate the definition of mass based on the new SI*
L.S. Chao, S. Schlamminger, D.B. Newell, J.R. Pratt, G. Sineriz, F. Seifert, A. Cao, D. Haddad, X. Zhang

== Todo ==

* Design physical balance structure
	* Use laser-cut acrylic instead of LEGO for structure.
	* What is the overall size? NIST Lego balance is approx 43 cm x 36 cm x 10 cm, with mass of 4kg. We can cut parts up to approx 60cm x 30 cm with laser cutter. How long do we want our balance arms?
	* Does heavy help? LEGO balance beam looks massively overbuilt, as does support tower. Is that a feature of building out of LEGO, or useful in overall design?
	* Idea: roughly T-shaped balance arm, with pivot point at T intersection. Arms hold mass pans, leg is a pointer that can be used for displacement measurement in center. Center of balance of balance arm below pivot, so self-righting when balanced. Need to check math to make sure extra torque isn't too great.
* Design electronics
	* NIST uses shadow sensor to measure position indirectly, calibrated with laser cast on wall. Use hall-effect linear sensor to measure position directly? AS5304 has precision of 25 μm, which is comparable to the error bars NIST shows. NIST photodiode costs $60+, AS5304 costs $8, and can be gotten as a sample for free.
	* NIST uses $$$ 6x ADC and 4x DAC units, which together cost over $300. In practice, they use two ADC and one DAC at a time, max, for analog work. Can we do equally accurate, but less expensive?
	* In NIST, the two coils are suspended from the mass pans. How do we route wires to them without throwing off balance? NIST paper doesn't say. Could we invert it, fixing coils on base and hang magnets from the mass pan? 
* Design software
	* NIST uses custom software on PC, and connects ADC/DAC units to PC via USB. 
	* Vic wants to use possibly multiple Arduinos to run this device. How will tasks be split between them?

