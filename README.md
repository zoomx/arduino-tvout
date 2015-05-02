# arduino-tvout
just a copy of the original repository but v-Sync-problem fixed.

Automatically exported from code.google.com/p/arduino-tvout

It is just a copy of the original repository
I only fixed vertical sync pulses as described in Issue 7 in Google Code
https://code.google.com/p/arduino-tvout/issues/detail?id=7

#5 lerrypag...@gmail.com Nov 26, 2013
I have fixed the v-Sync-problem in the video_gen.cpp on line 98

original: 
void vsync_line() {
	if (display.scanLine >= display.lines_frame) {
		OCR1A = _CYCLES_VIRT_SYNC;
		display.scanLine = 0;
Fixed:
void vsync_line() {
	if (display.scanLine >= display.lines_frame) {
		OCR1A = _CYCLES_VIRT_SYNC;
		display.scanLine = -1
