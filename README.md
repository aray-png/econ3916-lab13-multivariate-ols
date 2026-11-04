# Abigail Ray || Econ 3916 ||Multivariate OLS: What "Controlling For" Actually Does

## Objective
I used simulated data with a known truth to show what happens to a regression coefficient when a control is left out, added, or added by mistake.

## Methodology
- Simulated wages that depend on education and on unobserved ability, then ran a short regression (ability omitted) and a long regression (ability included).
- Checked the omitted-variable-bias formula (gamma × delta) against the actual bias.
- Showed Frisch-Waugh-Lovell by regressing the part of wages that ability does not explain on the part of education that ability does not explain, and compared the result with the full regression.
- Simulated a collider (two independent variables that both cause a third) and ran the regression with and without the collider as a control.
- Simulated two nearly identical regressors and used variance inflation factors to separate what multicollinearity damages from what it does not.
- Fitted an interaction between experience and union membership to let the return to experience differ by group.
- Asked an AI to write a specification-table function, revised my prompt once, and set up a check of its coefficients against my own regressions from Steps 2 and 5.

## Key Findings
- Leaving ability out gave a return to education of 5,126 against a true 2,500. Putting ability in gave 2,546.
- The bias formula predicted a bias of 2,629, and the actual bias was 2,626.
- The Frisch-Waugh-Lovell two-step gave 2,546.4985, the same coefficient as the full regression.
- A collider control turned a true effect of zero into an estimate of -0.596, with a p-value that printed as 0.000. Without the control, the estimate was 0.001.
- Multicollinearity made the standard errors about 12 times larger (VIF of 150.4). The two coefficients still added up to 5.009 against a true 5, so the estimates were not biased.
- A year of experience was worth 903 to non-union workers and 504 to union members. The interaction coefficient was -398.6, with a t-statistic of -25.3.
- In the take-home challenge, omitting income made the class-size effect -3.59 against a true -0.5, and omitting motivation made the training effect 5,338 against a true 2,000. Controlling for occupation gave a degree return of 6,107 against a true 20,000, because occupation is both a mediator and a collider.
- The AI's first specification table used classical standard errors without saying so. My second prompt made the standard-error type a visible setting.
