# SubJuicy

SubJuicy is a monophonic synthesizer based on subtractive synthesis featuring four different filters, effects and tremolo controls. The app was developed by means of the following libraries:
- [Vue.js](https://vuejs.org/)
- [Tone.js](https://tonejs.github.io/)

Moreover, [Web MIDI API](https://developer.mozilla.org/en-US/docs/Web/API/Web_MIDI_API) is employed to manage MIDI devices connection.

![SubJuicy synthesizer interface](/assets/SubJuicySynth.png)

## Synth Controls

## App Architecture and State Update
The app provides different types of controls enabling the user to find the desired parameters configuration and shape the sound as wanted. All the functional blocks integrated in the signal flow of the application were implemented as **Vue components**. The state of the synth is managed and updated within the **SynthDevice** component, which handles *sound generation* and *signal processing* by means of Tone.js library. Each component allows the user to interact with the application and update the parameters related to the corresponding signal processing functional block.  
**Vue watchers** are employed in order to automatically *update component data* and emit events to the parent SynthDevice. Indeed, any time parameters are changed from the user interface, data in the child component are automatically updated and the **onUpdateState event** is fired and sent to the parent. This event is attached to the **updateState function** which is implemented in SynthDevice component and responsible for *state update* based on the parameter name received from the child.

![Vue App Architecture](/assets/SubJuicySynth_AppArchitecture.png)

The diagram above shows how the architecture of the application is organized in vue components and parameters are passed from leave components to SynthDevice where the overall synth state is updated.

## Signal Flow
