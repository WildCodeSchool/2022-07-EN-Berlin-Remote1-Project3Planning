# Todo-centric UI design

## Background

### Goal

The purpose of the REMONDIS de-cluttering app is to allow decluttering companies with multiple people to work at a similar level of efficiency as the one-man-model *explained by one of the consultants in person (Sascha)*.

### Strategy

To achieve this goal, the strategy would be to reduce the amount of time it takes from the moment a household owner calls the decluttering company to the moment they have a quote ready.

Speaking from the perspective of the app, this translates to the time taken for a case to make its way from the [CREATED](https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Planning#de-cluettering-case-states) to the [QUOTED/CLOSED](https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Planning#de-cluettering-case-states) states.

### Theory

The time we are trying to reduce or optimise can be expressed mathematically as follows:

$$\begin{array}{ccl}
t_{\text{total}} &=& t_{\texttt{quoted}} - t_{\texttt{created}}\\ 
t_{\text{total}} &=& (t_{\texttt{confirmed}} - t_{\texttt{created}}) \\; + \\
 & & (t_{\texttt{made-appointment}} - t_{\texttt{confirmed}}) \\; + \\ 
 & & (t_{\texttt{inspected}} - t_{\texttt{made-appointment}}) \\; + \\ 
 & & (t_{\texttt{submitted}} - t_{\texttt{made-appointment}}) \\; + \\ 
 & & (t_{\texttt{quoted}} - t_{\texttt{submitted}}) \\  
t_{\text{total}} &=& t_{\text{a}} + t_{\text{b}} + t_{\text{c}} + t_{\text{d}} + t_{\text{e}}
\end{array} $$

**WHERE:**
- $t_{\text{a}}$ is the elapsed time after creating a case and before it has a confirmed _assigned inspector._ This duration can be made shorter by:
  - _manager_ assigning or re-assigning the case quickly
  - _inspector_ accepting or rejecting assigned case quickly
- $t_{\text{b}}$ is the elapsed time after confirming the assigned inspector to the case and before an appointment is made with the household owner. This duration can be made shorter by:
  - _inspector_ making an appointment with the household owner
- $t_{\text{c}}$ is the elapsed time after making an appointment and before the date/time of the appointment. **This duration cannot be made shorter.**
- $t_{\text{d}}$ is the elapsed time after the inspection appointment and before the data of the inspection is uploaded in the app and the case submitted. This duration can be made shorter by:
  - _inspector_ uploading the data and submitting the case.
- $t_{\text{e}}$ is the elapsed time after submitting the case and before the household owner receives a quotation. This duration can be made shorter by:
  - _manager_ sending the quote

### TODO's

From the above, we can easily conclude that different user roles present opportunities to optimise the total duration, or the key performance metric described above.

To take full advantage of this opportunity, it had been ***reached through unanimous decision*** that the UI should leverage, or take full advantage of these opportunities which we refer to as **TODO's**.

In a sense, a TODO is a _call to action_ which is pushed by the app to its user to ensure that the process of generating quotes is accomplished as quickly and as efficiently as possible.

#### Manager TODO's
- **Case created but not assigned.** 
  - _Functionality pushed by app:_ assign case to an inspector.
- **Case assigned but inspector did not confirm or reject.**
  - _Functionality pushed by app:_ either re-assign or call/message the inspector.
- **Case rejected by inspector.** 
  - _Functionality pushed by app:_ reassign case to another inspector.
- **Case confirmed but no appointment made.**
  - _Functionality pushed by app:_ Follow up on inspector to call the household owner to make an appointment.
- **Case inspected (appointment date passed) but data was not entered or submitted.** 
  - _Functionality pushed by app:_ Follow up on inspector to submit case for quotation.
- **Case submitted but not yet quoted.**
  - _Functionality pushed by app:_ Send a quote to the household owner.

#### Inspector TODO's
- **Case assigned to inspector but he did not accept or reject.**
  - _Functionality pushed by app:_ Accept or reject assigned case.
- **Case confirmed but no appointment made.**
  - _Functionality pushed by app:_ Call household owner or email them to make an appointment and enter it into the app.
- **Case inspected, appointment passed but data is not uploaded or case not submitted.**
  - _Functionality pushed by app:_ Upload data and submit case.
