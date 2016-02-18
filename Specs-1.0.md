# Timeline
Recurring app starts should bring the user back to where he left. The user should have context what he looked at when last using the app. That counts for the scroll position in the timeline and selected events.

## Initial loading
Load a maximum of 100 events. Show the loading spinner until the events are loaded and display them all at once. Don’t show multiple spinners, just one! This happens only when the timeline is empty like the first time opening the app.

## Pull to refresh
Drag down on timeline to update manually. Always fill the gap between last timestamp/event shown and most recent. Load a maximum of 100 events, if there are more events show a button “More Reports”.

## Updating
Automatically fetch new events upon app start, if the app hasn’t been used for a couple of days, always fill the gap between last timestamp/event shown and most recent. Load a maximum of 100 events, if there are more events show a button “More Reports”. Don’t show a spinner and consider to not trigger another fetch when the user is pulling to refreh. Also automatically check for new events every 3 minutes and eventually fetch them as long as the app is active or in background starting from the last refresh.

## Autoscroll
If scroll position is at the very top of the timeline autoscroll to the most recent event once they are fetched, so the user is kept at the top of the timeline. Do not autoscroll if scroll position is below the very top or the app is not active.

## Notifications
**iOS**: New timeline events trigger to display a badge number to the app icon (not a notification) for each new event.

**Android**: New timeline events trigger to display a notification with an incrementing number for new events.

The counter is to be updated every 3 minutes regarding the automatical check of new events. Once the app is opened remove the badge/notification. Don’t trigger the badge/notification as long as the app is active.

## Read state
An event has a read state that indicates whether or not the user has already viewed it. New events added to the timeline have the state 'unread' while those which have been viewed switch to 'read'. The read state doesn’t need to be shared across devices for nor to be changed due to some action for now.

## Annotation
The annotation cell has a maximum of two lines of text. Longer text will be truncated at the end. The full content of longer annotation text can be viewed in edit mode by tapping the annotation cell. If the user is only member of an app and thus doesn’t have sufficient rights to add or edit the annotation remove the abilities to do so and hide it from the crash group details if none is set yet.