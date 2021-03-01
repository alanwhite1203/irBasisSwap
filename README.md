# Understanding Basis Swap Valuation

Overview
A basis swaps is an interest rate swap that involves the exchange of two floating rates, where the floating rate payments are referenced to different bases. Both legs of a basis swap are floating but derived from different index rates (e.g. LIBOR 1 month vs 3 month).  Basis swaps are settled in the form of periodic floating interest rate payments. They are quoted as a spread over the reference index. For example, 3-month LIBOR is frequently used as a reference. Spreads are quoted over it. 
A basis swap can be used to limit interest rate risk that a firm faces as a result of having different lending and borrowing rates. Basis swaps help investors to mitigate basis risk that is a type of risk associated with imperfect hedging. Firms also utilize basis swaps to hedge the divergence of different rates. Basis swaps could involve many different kinds of reference rates for the floating payments, such as 3-month LIBOR, 1-month LIBOR, 6-month LIBOR, prime rate, etc. There is an active market for basis swaps. This presentation gives an overview of interest rate basis swap product and valuation model. 

	Keywords:
basis swap, interest rate swap, basis risk, OTC derivatives, swaplet, valuation, pricing model

	Interest Rate Basis Swap Introduction
	An interest rate swap is an agreement between two parties to exchange future interest rate payments over a set period of time.
	A basis swaps is an interest rate swap that involves the exchange of two floating rates, where the floating rate payments are referenced to different bases.
	Both legs of a basis swap are floating but derived from different index rates (e.g. LIBOR 1 month vs 3 month).Swaps are OTC derivatives that bear counterparty credit risk beside interest rate risk.
	Basis swaps are settled in the form of periodic floating interest rate payments.
	Basis swaps are quoted as a spread over the reference index. For example, 3-month LIBOR is frequently used as a reference. Spreads are quoted over it.

	The Use of Interest Rate Basis Swap 
	A basis swap can be used to limit interest rate risk that a firm faces as a result of having different lending and borrowing rates.
	Basis swaps help investors to mitigate basis risk that is a type of risk associated with imperfect hedging.
	Firms also utilize basis swaps to hedge the divergence of different rates.
	Basis swaps could involve many different kinds of reference rates for the floating payments, such as 3-month LIBOR, 1-month LIBOR, 6-month LIBOR, prime rate, etc.
	There is an active market for basis swaps


	Basis Swap or Basis Swaplet Payoff
	From the leg 1 receiver perspective, the payoff of a basis swap or basis swaplet at payment date T is given by
〖Payff〗_payer=Nτ((R_1-R_2)
where 
N- the notional;
 τ – accrual period in years (e.g., a 3 month period ≈ 3/12 = 0.25)
R_1 – the floating rate of leg 1 in simply compounding.
R_2 – the floating rate of leg 2 in simply compounding.
	From the leg 1 payer perspective, the payoff of a swap or swaplet at payment date T is given by
〖Payff〗_payer=Nτ((R_2-R_1)

	Valuation
	The present value of  leg 1 is given by
〖PV〗_1 (t)=N∑_(i=1)^n▒〖(F_1i+s_1 ) τ_i D_i 〗
where 
t is the valuation date
D_i=D(t,T_i) is the discount factor.
F_1i=(D_(i-1)/D_i -1)/τ_i is the simply compounded forward rate 
s_1 is the floating spread.
	The present value of leg 2 is given by
〖PV〗_2 (t)=N∑_(i=1)^n▒〖(F_2i+s_2 ) τ_i D_i 〗


	The present value of an interest rate swap can expressed as
	From the leg 1 payer perspective, PV=〖PV〗_2-〖PV〗_1		
	From the leg 1 receiver perspective, PV=〖PV〗_1-〖PV〗_2

	Practical Notes
	First of all, you need to generate accurate cash flows for each leg. The cash flow generation is based on the start time, end time and payment frequency of the leg, plus calendar (holidays), business convention (e.g., modified following, following, etc.) and whether sticky month end.
	We assume that accrual periods are the same as reset periods and payment dates are the same as accrual end dates in the above formulas for brevity. But in fact, they are different due to different market conventions. For example, index periods can overlap each other but swap cash flows are not allowed to overlap.
	The accrual period is calculated according to the start date and end date of a cash flow plus day count convention 
	The forward rate should be computed based on the reset period (index reset date, index start date, index end date)  that are determined by index definition, such as index tenor and convention. it is simply compounded.
	Sometimes there is a floating spread added on the top of the floating rate in the floating leg.
	The formula above doesn’t contain the last live reset cash flow whose reset date is less than valuation date but payment date is greater than valuation date. The reset value is
〖PV〗_reset=r_0 Nτ_0 D_0  
where r_0 is the reset rate. 
	The present value of the reset cash flow should be added into the present value of the floating leg.
	Some dealers take bid-offer spreads into account. In this case, one should use bid curve constructed from bid quotes for forwarding and offer curve built from offer quotes for discounting.

	A Real World Example
Leg 1 Specification	Leg 2 Specification
Currency	USD	Currency	USD
Day Count	dcAct360	Day Count	dcAct360
Leg Type	Float	Leg Type	Float
Notional	10000000	Notional	10000000
Pay Receive	Receive	Pay Receive	Pay
Payment Frequency	6M	Payment Frequency	6M
Start Date	7/16/2015	Start Date	7/16/2015
End Date	7/16/2020	End Date	7/16/2020
Spread	0.0020625	Spread	0
Index Specification	Index Specification
Index Type	LIBOR	Index Type	LIBOR
Index Tenor	3M	Index Tenor	6M
Index Day Count	dcAct360	Index Day Count	dcAct360



You can find more details at
https://finpricing.com/faq.html

