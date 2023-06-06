# appAGMgeek_bot

Sample1: https://stackoverflow.com/questions/30833844/get-holidays-list-of-a-country-from-google-calendar-api

[Picked] Sample2: https://stackoverflow.com/questions/43671564/check-if-date-is-a-holiday-in-google-sheets

Analysis2: https://chat.openai.com/share/5104087b-71c6-4162-871c-5d01059dd753

------------

WRONG CODE: 

  var today = new Date();  
  var events = Calendar.Events.list(calendarId, {
    timeMin: today.toISOString(),
    timeMax: today.toISOString(),
    singleEvents: true,
    orderBy: 'startTime'
  }).items;
  var event = events[i];  
  var summary = event.summary.toLowerCase();  
  if (summary.includes('holiday') || summary.includes('public holiday')) { }  
  
