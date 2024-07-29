# FullCalender-ExternalEvent
for Netsofter LLP


```javascript
        document.addEventListener('DOMContentLoaded', function() {
            var calendarEl = document.getElementById('calendar');
            var externalEventsEl = document.getElementById('external-events');

            // Initialize the calendar
            var calendar = new FullCalendar.Calendar(calendarEl, {
                headerToolbar: {
                    left: 'prev,next today',
                    center: 'title',
                    right: 'dayGridMonth,timeGridWeek,timeGridDay'
                },
                editable: true,
                droppable: true, // Allow dragging events to the calendar
                drop: function(info) {
                    if (info.draggedEl) {
                        var eventData = {
                            title: info.draggedEl.innerText,
                            start: info.dateStr
                        };
                        calendar.addEvent(eventData);
                    }
                }
            });

            calendar.render();

           
            

            new FullCalendar.Draggable(externalEventsEl, {
                itemSelector: '.fc-event',
                eventData: function(eventEl) {
                    return {
                        title: eventEl.innerText
                    };
                }
            });



        });

```
