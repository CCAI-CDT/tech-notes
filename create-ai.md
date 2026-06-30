<!-- spell-checker:words CreateAI microbit -->

# Create AI

You will need:

* A computer
* BBC micro:bit v2
* USB A to micro-B cable (and a USB C to USB A adapter if your computer only has USB C ports)
* Battery pack with AAA batteries
* (Optional) micro:bit wearable strap


## Connecting

1. Visit the *Create AI* website at [createai.microbit.org](https://createai.microbit.org/) in a browser that supports *WebUSB* / *WebBluetooth* (e.g. a Chromium-based browser like Chrome).
2. Click *+ New Project*, enter a name for your project, and *Create Project*.
3. Click *Connect* then, if shown, *Connect using Web Bluetooth instead*, then follow the instructions to connect your micro:bit wirelessly.


## Training

1. Click the drop-down arrow (`▼`) next to the icon and choose an icon for your first action.
2. Give your action a name.
3. Click *Record* and follow the instructions to record an example action.
4. Repeat the recording samples, and delete any samples that appear to be incorrect (`✖`).  You must have at least 3 samples for each action.
5. Click *+ Add action* to add a second action, and repeat the process to record samples for that action.
6. Optionally add additional actions and samples.
7. Click *Train model* and *Start training* to train the AI model to recognize your actions.


## Using the model

1. Follow the on-screen instruction and test your actions and the model's response.
2. When you are ready, click *Edit in MakeCode*
3. Use the MakeCode blocks editor to create a program that uses your trained model.  You can use the *on ML (action) start* blocks to trigger events based on the actions you trained.  
  * For example, you can play audio on the micro:bit V2 by adding the *Music*/*play (sound) until done* block.
4. To test your program, click *Download* in the lower-left corner.



## See also

* *RAISE*: [playground.raise.mit.edu](https://playground.raise.mit.edu/)
