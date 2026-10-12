# Cleaning Log: Certified Organic Livestock

Source: certified_organic__livestock_analysis.xlsx (raw file untouched; all work in Google Sheets)

## 1. State Organic Livestock: 2011 blanks

Issue: 86 blank cells in the 2011 block (I:N). They behave as zeros.

P9:T58 hold the raw 2011 counts from I9:M58, with every blank cell converted to 0.
The raw columns I:N are left untouched.

Formula used in P9, filled across to T9 and down to row 58:
`=N(I9)`

Action: returns the number in I9, or 0 if I9 is blank.
Check: `=COUNTBLANK(P9:T58) = 0`; `=COUNTIF(P9:T58,0) = 82`; `=U7 - N7 = 0`.

Formula (U9, filled down to row 58):
`=SUM(P9:T9)`
Action: adds the five clean 2011 columns to give the clean total.

Formula (V9, filled down to row 58):
`=IF(COUNTA(I9:M9)=0,"No 2011 data",IF(COUNTBLANK(I9:M9)>0,"Partial blanks","Complete"))`
Action: labels each state by how much of its 2011 block is blank.

Checks: U7 - N7 = 0; flags 4 / 29 / 17, total 50, PASS.

## 2. Certifiers

Issues found included mixed-sentence case,  padded names and whitespaces

Formula(H4, filled down to row 62):`=IFERROR(REGEXEXTRACT(B4,"\((.*)\)"),"") `Action: extracts the text inside the first pair of brackets. 

 Formula(I4, filled down to row 62): `=PROPER(TRIM(REGEXREPLACE(B4,"\(.*\)","")))`
Action: trimmed all whitespace,brackets are removed and capitals standardized

Formula(J4, spills across L4, and down to row 62):`=ARRAYFORMULA(SPLIT(C4:C62,","))`
Action:Split the Headquarters in C into city,state and region(J4:L62)

Formula(M4, filled down to row 62):`=IF(REGEXMATCH(LOWER(H4),"revok"),"Revoked",IF(REGEXMATCH(LOWER(H4),"surrender"),"Surrendered","Active"))`
Action: reads the note in H4 and returns "Revoked" if it contains "revok",
"Surrendered" if it contains "surrender", otherwise "Active".
Checks: Active 48; Surrendered + Revoked 11; total 59.

## 3. Manual patches

- Cell I34: Ecocert ICO name restored by hand (bracket is part of the name, not a status)
- Column I was pasted as values, so that Find and Replace could be used  on "Of">"of" and "And">"and"
- Cell I23: Virginia "2/" left in place (footnote marker, known issue)

## 4. Known issues

- Column I is values only and will not update if column B changes
