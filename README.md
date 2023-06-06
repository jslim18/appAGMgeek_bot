# appAGMgeek_bot

Sample1: https://stackoverflow.com/questions/30833844/get-holidays-list-of-a-country-from-google-calendar-api

[Picked] Sample2: https://stackoverflow.com/questions/43671564/check-if-date-is-a-holiday-in-google-sheets

Analysis2: https://chat.openai.com/share/5104087b-71c6-4162-871c-5d01059dd753

WRONG CODE:

function isPublicHoliday() {
  var today = new Date();
  var calendarId = 'your_calendar_id';
  
  // Call the Google Calendar API
  var events = Calendar.Events.list(calendarId, {
    timeMin: today.toISOString(),
    timeMax: today.toISOString(),
    singleEvents: true,
    orderBy: 'startTime'
  }).items;
  
  // Check if any events are found
  if (events.length > 0) {
    for (var i = 0; i < events.length; i++) {
      var event = events[i];
      var summary = event.summary.toLowerCase();
      
      // Check if event summary contains public holiday keywords
      if (summary.includes('holiday') || summary.includes('public holiday')) {
        Logger.log('Today is a public holiday!');
        return true;
      }
    }
  }
  
  Logger.log('Today is not a public holiday.');
  return false;
}
