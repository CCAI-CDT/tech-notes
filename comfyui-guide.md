<!-- spell-checker:words SDXL denoise -->
<!-- spell-checker:ignore dpmpp_2m -->

# ComfyUI Starter Guide

### Install it, run it, make your first AI image

ComfyUI is a free, node-based app for generating images on your own machine. You wire together a few boxes ("nodes") into a graph, hit a button, and it produces an image. This sheet takes you from nothing to your first picture.

---

## ⚠️ Step 0 — Check your hardware first

ComfyUI itself is tiny. The image _models_ are what need power — specifically a graphics card (GPU) with enough video memory (VRAM).

| Your situation            | What you can run                 | Realistic speed                  |
|---------------------------|----------------------------------|----------------------------------|
| NVIDIA GPU, 4–6 GB VRAM   | SD 1.5 models (lighter)          | ~10–30s per image                |
| NVIDIA GPU, 8 GB+ VRAM    | SDXL models (recommended start)  | A few seconds to ~30s per image  |
| NVIDIA GPU, 12 GB+ VRAM   | Everything, including Flux       | Fast                             |
| Mac (Apple Silicon, M1+)  | SDXL / SD 1.5, slower            | Tens of seconds                  |
| No GPU / old laptop       | CPU only (very slow)             | Several minutes per image        |

> **No suitable GPU?** The Desktop app can technically still run on the CPU, but a single image may take several minutes — fine for a one-off try, too slow to enjoy. You'll get a much better experience on a machine with an NVIDIA GPU or Apple Silicon.

To check on Windows: press `Ctrl+Shift+Esc` → Performance tab → GPU. On Mac, anything M1 or newer is fine.

---

## Step 1 — Install ComfyUI (Desktop app)

The official installer that works like any normal program. Available for **Windows and macOS**.

1. Go to [**comfy.org**](https://comfy.org/download) and download **ComfyUI Desktop** for your operating system.
2. Run the installer and click **Get Started**. It sets up everything it needs (including its own Python) automatically.
3. Wait for it to finish — the first launch may download some setup files, so give it a few minutes.
---

## Step 2 — Setup ComfyUI 

1. Open Comfy Desktop.
2. On the question "How do you want to run Comfy UI" select "Local".
3. Tick "Express install with recommended settings"
4. Tick "I agree to EULA..."
5. Untick "Send anonymous data...."
6. Press continue.

ComfyUI will now do the final setup, it might take a while. Once its done a graph view will be visible or a new window called "Templates" with "Getting Started" text.

## Step 3 — Make your first image

We will now guide you through the steps for generating on first image.

1. This step will depend of your installation and what is on your screen once the setup is done. 

   If you see a new window called "Templates" with "Getting Started" text: proceed to the next step.

   If you only see a graph view with nodes and edges do the following:

	1. Click on the "C" button on the left side of the screen.

		![Templates Window](images/Screenshot%202026-06-26%20at%2010.17.55.png)
	2. Click "Browse Templates"
	3. A new window called "Templates" with "Getting Started" text show now be visible.

2. With the "Templates" window open, on the search bar type: "Image Generation" and click on the result. The searched template to click is the following:

	![Image Generation tile](images/Screenshot%202026-06-26%20at%2009.52.46.png)

3. A new workflow will open, and a error pop up will appear.

4. On the error pop-up click "Show missing models".

5. A new panel on the window will appear, saying there are missing models, press "Download All".

6. A new alert will appear on the right of the screen on a download icon with a blue border, this means ComfyUI is currently downloading the missing models. You can click on that button to see  the current download status.

7. Once the download icon turns to green the model as been downloaded.

8. You can now close the panel with the "Download All" button by pressing this button on the right of the screen:

	![Close panel icon](images/Screenshot%202026-06-26%20at%2010.08.49.png)

9. Everything is now be set to generate your first image. Press "Run" to generate a image.

	![Run button](images/Screenshot%202026-06-26%20at%2010.09.16.png)


## Step 3 — Understanding how to generate images

Now that you generated a your first image lets understand how ComfyUI works. On you can zoom in the graph view to find the following nodes with the following features:

1. **Load Checkpoint** → click the dropdown and pick a model you downloaded.

2. **Positive prompt** (the green text box) → type what you want to generate. Example:

    > `cinematic photo of a red panda sitting on a mossy rock, golden hour light, shallow depth of field, highly detailed`

3. **Negative prompt** (the red text box) → type what you don't want to generate. Example:

    > 	`blurry, low quality, extra limbs, text, watermark`

4. **Empty Latent Image** → set the size of the image to be generated. For SDXL use **1024 × 1024** (other same-area sizes like 896×1152 also work well). For SD 1.5 use **512 × 512**.

5. **KSampler** → set properties of the image generation. The following properties are present:

	* **seed** — the random starting point, shown as a long number. The same seed with the same settings and prompt always produces the _same_ image. Think of it as a dice roll: change it and you get a different result.

	* **control_after_generate** — what happens to the seed after each run. `randomize` gives a fresh image every time (good for exploring); `fixed` keeps it identical (good when you want to repeat or fine-tune one image).

	* **steps** — how many passes it takes to turn noise into a finished image. More steps = more detail but slower, with little benefit past a point. **~20–25 is a good default.**

	* **cfg** — how strictly the model obeys your prompt. **Low** (~3–5) = looser and more creative; **high** (~10+) = very literal but can look harsh, **~7 is a sensible start.**

	* **sampler_name** — the method used to remove the noise. Different samplers give slightly different looks and speeds.**`euler` or `dpmpp_2m` are safe defaults.**

	* **scheduler** — controls the _pace_ at which noise is removed across the steps. It pairs with the sampler. **`normal` or `karras` are common; `karras` often looks a little cleaner.**

	* **denoise** — how much of the image is created from scratch. **Leave it at 1.0** for normal text-to-image. (Lower values keep part of an existing image and are used later for image-to-image editing.)

6. **VAE Decode** → the KSampler doesn't output a picture you can see — it works in a compressed, behind-the-scenes form called a **latent** (the image as maths, faster to work with). VAE Decode is the translator that turns that latent into the actual viewable image. **You don't need to touch this** — the VAE it uses comes bundled inside the model you loaded. The only time it matters is if images come out washed-out or oddly coloured, which can mean you need to load a separate VAE.

7. Save Image → Saves the image into the default folder.

	On macOS, this will be:
	```
	/Users/(user name)/ComfyUI-Shared/output
	```

---

## Step 4 — Where to go next

- **Try a different prompt**.
- **Change the seed** and re-queue to explore variations of the same prompt.
- **Try another template**

---
