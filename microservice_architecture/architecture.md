we have few ms for this app:

- IAM (ms using a db)
- userDetails: (ms using db)
  * basic user details as addresses, phone, mails etc.
  * past jobs
  * income history
- searchBox (will be included in th userDetails ms due to similar functionality)
- ID validation (ms)

the patterns i chose:
ms - Besiness Capabilities:
    i chose this pattern due to the simplicity of the system - first theres the IAM responsibility, second is the user, Which is the main Actor in the system so he gets a independent MS to handle all of the data and searches, and finally the main functionality of the system - the Id validation (may interact with third party apps like the goverment or so)

db - Database per service
    i belive the most important issue for a banking system is to secure the data of the customers. regarding to the scatch of the system above, i would seperate the IAM db and the userDeatils' db, eventhogh ill probably have to duplicate some of the user's info.

observability patters - 
    for this specific system, if i should pick only one pattern, i belive the most relevant is the Health check pattern.
    when you dealing with a bank system, the most important matter is the banks reputation, having said that, i belive the system should have minimum down time,
    and whenever that happends i want to be able to monitor this ASAP.
