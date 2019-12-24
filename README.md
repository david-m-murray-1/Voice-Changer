# Voice-Changer
Voice modulation to simulate a desired voice in real time.

/* Voice Changer
   Changes a person's voice from a microphone recording to match another voice loaded via mp3 audio input
   1. Input an audio stream y1(t) that you want to match your voice to.
   2. Input a second audio stream x1(t) a 5 second recording via microphone.
   3. Signal Analysis (FFT --> smooth desired voice signal --> signal analysis of the 2 input signals --> IFFT)
   4. Flash an LED once the transfer function has been determined.
   5. Talk into the microphone and convolve the microphone audio input x2(t) by transfer function to produce
      audio output stream y2(t).
*/

/* Program Flow
   1. OLED: "Press button 1 to record desired voice to be simulated"
   2. button 1 pressed: audio input y1(t) is recorded to EEPROM for 5 seconds
   3. OLED: "Voice recorded. Repeat the words produced by the speaker"
   4. EEPROM file sent to audio output jack to speaker
   5. OLED: "Playing desired voice."
   6. OLED: "Press button 2 when you are ready to record your voice."
   7. button 2 pressed
   8. OLED: "begin speaking into the microphone to begin recording your voice"
   9. Begin recording user voice to EEPROM when microphone detects a signal above the threshold (this part is analog circuitry driven)
   10. User mic LED turns off after 5 seconds of writing user voice to EEPROM
   11. OLED: "Transfer function determined. Begin speaking to simulate the desired voice."
   12. audio output of simulated voice y2(t) to speaker - convolved user voice x2(t) and transfer function h1(t)
*/
