# SubJuicy

SubJuicy is a monophonic synthesizer based on subtractive synthesis featuring four different filters, effects and tremolo controls. The app was developed by means of the following libraries:
- [Vue.js](https://vuejs.org/)
- [Tone.js](https://tonejs.github.io/)

Moreover, [Web MIDI API](https://developer.mozilla.org/en-US/docs/Web/API/Web_MIDI_API) is employed to manage MIDI devices connection.

![SubJuicy synthesizer interface](/assets/SubJuicySynth.png)

## Synth Controls
The app provides different types of controls enabling the user to find the desired parameters configuration and shape the sound as wanted. All the functional blocks integrated in the signal flow of the application were implemented as Vue components. The state of the synth is managed and updated with the SynthDevice component, which handles sound generation and signal processing by means of Tone.js library. Each component allows the user to interact with the application and update the parameters related to the corresponding section. Vue watchers are employed in order to automatically update them and emit onUpdateState event to the parent component which is SynthDevice one.

## Signal Flow
