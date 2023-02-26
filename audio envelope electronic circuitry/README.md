# Enveloppe detection

The purpose of this circuit was to get rid of the digital audio output of the KY-038 audio detector : this output is not a real digital signal but rather a audio signal passed through a digital comparator. As a result, the output is not a boolean signal indicating the presentce or absence of audio, but ,let's say, a 800Hz 0-3.3 V oscillation.

One possible solution to build a low-pass filter, but we'd lost the sharpness of the audio signal (as morse keying, or DCF77 clock signal).

The choice was to build a retriggerable monostable timer, with NE555.
- Q1 is used to retrigger the pluse each audio period.
- once the audio signal disappear, the (about) 2ms pulse run until completion.
- Q2 is used to change the NE555 5V output to 3.3V raspberry pico input.
