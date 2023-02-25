# NotePlayer
NotePlayer uses a specific syntax to convert notes into sound using MIDI. See the example transrciption file to see an epic MIDI rendition of some Kirby's Return to Dreamland Boss Music.
## Individual Note Formatting
![image](https://user-images.githubusercontent.com/108494599/221381414-c4340ccb-9233-4ad5-93b9-c4b75f587b50.png)  
*The duration is in miliseconds.*
## Playback Adjustment
Each song is entered as a single line containing:
•	an optional “playback adjustment” followed by a comma (“,”), and then
•	a list of note symbols with a space (“ “) between them
The following is an example, with the playback adjustment in italics and the list of note symbols shown in bold:  
  
*4_2.3*,**Ab3_600 B-2_450 Db5_150 G#_5 E_300 D#-1_10**

The playback adjustment contains two parts:
1.	A transpose adjustment integer
2.	A tempo adjustment double 
<!-- end of the list -->
For example, here is a playback adjustment with the transpose (4) in bold, and the tempo (2.3) in italics:  
**4**_*2.3*  
  
The “transpose” adjustment is a number that is added to every note present in that song’s note list.  This can be used to raise or lower the pitch of the entire song.  For example, if you calculated that the MIDI Note Numbers for a song are 12, 14, 16, and the transpose adjustment is 4, then you’d add 4 to each MIDI Note Number.  
  
The “tempo” adjustment is a number that is multiplied with every note duration present in the song’s note list.  For example, if the note durations in the note list were 100, 200, 149, and the tempo adjustment is 2.3, then you’d multiply 2.3 with each note duration.  
  
For example, you can speed up the song by using a tempo adjustment of 0.5 (to play in half the time), or slow down the song by using a tempo adjustment of 2 (to double the length).  The tempo adjustment can be any positive double (less than 1 would speed up the song, greater than 1 would slow it down).
The entire playback adjustment is sometimes present, but not always.  You are guaranteed to see either both parts or neither (i.e., you will never see a transpose without a tempo, or a tempo without a transpose).
A playback adjustment applies only to the line (note list) that it appears on.  It affects every note played from that list, but has no effect on any future lines entered by the user.
  
## Commands
### List Instruments
Type *list instrument* in the console to see a list of 127 different instruments.
### Set Instrument
Type *set instrument <int [0-127]>* to choose an instrument.  
For example:
  
*set instrument 26*
  
would set the jazz guitar to be the currently used instrument.  


