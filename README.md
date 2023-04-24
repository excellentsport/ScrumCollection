# ScrumCollection

Labview software for data collection on our custom scrum machine. Currently set up with dummy calibration numbers so that it displays something close to accurate. However, raw voltage values are saved so that voltages can be later transformed to force.

## Requirements

Requires Labview 2016 or greater.

## How to use for data collection

- Program starts paused, and simulated signals (sine waves) are generated for each of the cells. On the "Settings" Tab in the lower left, you must select which load cells you wish to display on the main "Summed Signal" graph and you must also click the toggle for "Are you collecting data?".
- Click back to the "Data collection" tab.
- Drag cursors on “Summed Signal” Graph to about ⅓ and ⅔, across graph
- Use “Start/Stop Collection” button to start saving or stop saving a file
  - Indicator light “Collecting” shows if data is currently being saved
- Use “Pause datastream” to stop progression of data in main graph
  - Note that this only pauses data in the graph- data is still streaming through A/D card etc. Use this button ONLY WHEN NOT SAVING DATA.
- To save a new trial:
  - Click “Start/Stop Collection”
    - This will prompt a new file save dialog, but will not initiate the new collection until you hit “OK”. Do this EARLY, so that all you have to do is click “OK” just before subject does next trial.
  - Navigate to your save folder
  - Name your file but don't hit okay yet...
  - When subject is ready to start, hit “OK”, and verify that “Collecting” indicator is green.
  - Subject will settle in, get hands up, and after they are in position and force trace is levelled off, then give thumbs up to person doing timing.
  - Click “Start/Stop Data Collection” ONLY after you have seen force trace drop back below force level during setup.
- If you want to inspect the force trace immediately, hit the “Pause datastream” immediately after stopping collection.
  - Drag cursors around as necessary to encapsulate beginning and end of trace. 
  - I suggest putting the yellow cursor at point where the ready position force trace is first stabilized, and blue cursor when pull is back below starting.

## How to use for calibration

- On the "Settings" Tab in the lower left, click the toggle for "Are you collecting data?". This will suppress the simulated sine waves generated on the load cells.
- Repeat the following process for each load cell and load you are calibrating:
  - Add the load onto the cell you're calibrating, then wait for the signal to advance across the graph. It will take 20 seconds to advance across. During this period, do not touch the load, walk around or do anything that could create vibration or loading that might be picked up by the cell. If anything is picked up (by a closing door nearby or otherwise), wait an additional 20 seconds.
  - Once the 20 seconds has elapsed, the signal will appear to become extremely noisy. This is due to the autoscaling feature on the graph - it is totally normal. This will also make it easier to detect any anomolous readings from outside sources.
  - Double click the number found in the "Mean Value for Last 20 sec" box to select, then hit "CTRL + C" to copy. Paste this value in as your output voltage to whatever spreadsheet you're using for the deadweight calibration.
- Repeat the process for each load and each load cell.
 