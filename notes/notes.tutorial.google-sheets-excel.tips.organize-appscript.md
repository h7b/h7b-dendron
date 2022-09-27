---
id: 5qWfZgO0gRlSIQoh1cB4F
title: Organize Appscript
desc: ''
updated: 1653346537517
created: 1644525406032
---
# Organize Google Apps Script in Google Sheets

ref: [NummeriBlog](https://thierryvanoffe.com/google-apps-script-et-google-sheets-centraliser-un-script-a-laide-dune-bibliotheque/), [Romain Vialard](https://romain-vialard.medium.com/deploy-easily-with-the-new-google-apps-script-ide-69343c71a889)

Situation: if I have to develop a script for many users in Google Sheets, how should I centralize it and maintain

![situation](https://docs.google.com/drawings/u/0/d/sTnMNh6DeqgqeYuG8ZqbU_w/image?w=567&h=528&rev=127&ac=1&parent=1PQDRVcYfutDN7FXZRLyClL3P_ZliKfEqir9rT44uicg){max-width: 300px, display: block, margin: 0 auto}

How to do?
1. create a google sheets template file for all users. Ask them to duplicate this file for their usage
2. create your custom script
  ![script-library](https://thierryvanoffe.com/wp-content/uploads/2021/01/image-4.png){max-width: 300px, display: block, margin: 0 auto}
3. make a new Deployment of your script as a [reusable code Library](https://developers.google.com/apps-script/guides/libraries) for others to use
  ![deploy-script-1](https://miro.medium.com/max/875/1*H0bnXd7zpMSoh9M_TlQgdQ.png){max-width: 300px, display: block, margin: 0 auto}
  ![deploy-script-2](https://miro.medium.com/max/875/1*CiEpugIfLYoD9uScH-RhWg.png){max-width: 300px, display: block, margin: 0 auto}
4. copy the Deployment ID
  ![deployment-id](https://miro.medium.com/max/875/1*dOU5cVnq8j8_IHVv3WTvKQ.png){max-width: 300px, display: block, margin: 0 auto}
5. add the Library into your google sheets template file
  ![add-to-file](https://thierryvanoffe.com/wp-content/uploads/2021/01/Ajout-bibliotheque-1.gif){max-width: 300px, display: block, margin: 0 auto}
6. DONE. Now you can use the functions from your custom Library
  ![result](https://thierryvanoffe.com/wp-content/uploads/2021/01/Usage-bibliotheque-1.gif){max-width: 300px, display: block, margin: 0 auto}

## Related resources

[Spreadsheet Dev | 5+ ways to run Google Apps Scripts in Google Sheets](https://spreadsheet.dev/5-plus-ways-to-run-scripts-in-google-sheets)
