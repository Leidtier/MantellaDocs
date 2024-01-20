# Installation
## Video Tutorial
For a visual reference to help install Mantella, see here (the video is in French with English subtitles):

```{eval-rst}
..  youtube:: v=-zRj2zFvGo0
```

%[youtube.com/watch?v=-zRj2zFvGo0](https://www.youtube.com/watch?v=-zRj2zFvGo0)

Note that xVASynth does not need to be run before Mantella.exe, and the bugs mentioned in the video have since been fixed.

## Requirements
### Hardware Requirements
There are no discovered minimum requirements at the time of writing for Mantella, but there has been a report of Mantella crashing when running a modlist of 2000 mods. Mantella needs a certain amount of hardware allocation to run successfully, and if this is being soaked up by other hardware intensive mods, it may crash.

The minimum requirements for xVASynth can be found on its [Steam page](https://store.steampowered.com/app/1765720/xVASynth/). It runs in CPU mode by default, using a single CPU core/thread. Only supports GPU acceleration on NVIDIA cards that have CUDA. Using the same GPU as the game will produce stutter, especially if it can't allocate ~2 GB of VRAM. You may try using an older NVIDIA card that has CUDA on another free PCI-Express slot of your PC and run any CUDA enabled services on that.

### Storage Requirements
This mod requires ~27GB of space when xVASynth and all voice models are installed. Temporarily another ~17GB is needed to unpack the voice models, unless the torrent is used which does not have the voice files archived.


### Compatibility
- Some users have reported that Skyrim crashes when Mantella is used with Fuz Ro D'oh. A possible fix is to disable and re-enable Fuz Ro D'oh
- The mod VR Keyboard conflicts with Mantella
- Mantella requires Windows 10 / 11 (it is yet unconfirmed whether it works on Windows 7)
- Mantella has been confirmed to work with the FUS (by pointing skyrim_folder to Skyrim), Librum (by pointing skyrim_folder to overwrite/root), and Wildlands (by pointing skyrim_folder to Wildlander/SKSE) , and Nolvus Wabbajack modlists.
- Mantella needs to be loaded after the Unofficial Skyrim Special Edition Patch (USSEP) mod in your load order
- GPU acceleration is only possible with CUDA enabled NVIDIA GPUs

### Skyrim
As Mantella accesses and writes to files within your Skyrim folder, it is unlikely to work correctly if you have Skyrim stored in Program Files. Please ensure that you have Skyrim stored outside of this folder (Such as C:\Games\Steam for example).

If you use the Steam version of Skyrim, then note that Steam does not allow to move the old or create a new Steam Game Library on the same disk partition by simply ignoring the attempt to do so. You either move the whole Steam client outside [as described on this Steam Support page](https://help.steampowered.com/en/faqs/view/4BD4-4528-6B2E-8327) or use [LostDragonist/steam-library-setup-tool](https://github.com/LostDragonist/steam-library-setup-tool/wiki/Usage-Guide) to create a Steam Game Library besides another.

### Mantella Files
The Mantella files can be downloaded from [Nexus Mods](https://www.nexusmods.com/skyrimspecialedition/mods/98631).

#### Mantella Software
Extract this folder somewhere convenient to you (if you need some inspiration, I have it stored in Documents). Do not store this folder in Program Files / (x86) or in your Skyrim folder.

#### Mantella Spell
This file can be installed in the same way as other mods with your mod manager.

## Whisper
guillaumekln's Faster-Whisper version of Whisper is used as Speech-To-Text engine by Mantella. The engine is **already part of the executable** and will download a chosen model automatically when launched. Uses a single CPU core by default when listening to the set default Windows microphone. Alternatively text input can be enabled by setting `microphone_enabled = 0` within _config.ini_ file.

It is reasonably fast even in CPU mode with the base model. _**Optionally**_ to use GPU/CUDA mode, some extra files are required, see [Faster Whisper documentation](https://github.com/guillaumekln/faster-whisper#gpu). Note that _cuBLAS_ may already be part of the CUDA Toolkit, so you may only require the _`cudnn_###_infer64_8.dll`_ files to be beside the Mantella executable. Afterwards enable `process_device = cuda` under `[Microphone]` within Mantella's _config.ini_.

## xVASynth
xVASynth is used as Text-To-Speech engine by Mantella due to being free open-source software and already having Skyrim voice models trained.
1. Download xVASynth via [Steam](https://store.steampowered.com/app/1765720/xVASynth/) or [Nexus](https://www.nexusmods.com/skyrimspecialedition/mods/44184). Do not store xVASynth in your Skyrim folder.

2. Download xVASynth trained voice models of Skyrim for all or any characters that you are likely to encounter. If downloading all models sounds a bit daunting, you can start with the "Male Nord" and "Male Soldier" voice models to at least allow talking to Skyrim guards. You can either download all models via a torrent, via the xVASynth UI if you have Nexus Premium, or manually via the Nexus Mods page.  

	<details>
	<summary><b>xVASynth Model Installation Options</b></summary>  

   	#### 💎 Nexus Premium (Quickest)  
   	If you are subscribed to Nexus Premium, open the xVASynth UI and select "Get More Voices" from the bottom left corner. Unselect all games except for Skyrim and download all models. Note that this may require restarting a few times for the downloads to properly complete.  

   	#### 🌊 Torrent (Slowest, Easiest)  
   	Voice models can be downloaded via a single torrent. Torrents can be downloaded via Bittorent clients such as [qBittorent](https://www.qbittorrent.org/download). Note that download speeds vary depending on the time of day. Paste the below magnet link in your browser to receive a popup to open it via your Bittorent client, and set the download location to your_xVASynth_folder/resources/app/models/skyrim:  

   	`magnet:?xt=urn:btih:798BB3190E776BFDCF590910C0805656420F45BC&dn=skyrim&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337&tr=udp%3a%2f%2fexplodie.org%3a6969&tr=wss%3a%2f%2ftracker.btorrent.xyz&tr=wss%3a%2f%2ftracker.openwebtorrent.com`  

   	Note that this magnet URI may be removed from this page if any voice model becomes unavailable on Nexus Mods.  
   
	#### 🛠️ Manual (Hardest)  
   	If you do not have Nexus Premium, or if the torrent is not available, you can also download the voice models directly from Nexus [here](https://www.nexusmods.com/skyrimspecialedition/mods/44184?tab=files) (under "Optional", not "Old). Once you have manually downloaded each voice model into a folder, open xVASynth and drag all zipped voice model files from this folder into the voices panel. Wait for the installation to complete (this may take some time; a popup will display when finished saying "x models installed successfully"). If this method doesn't work for you, you can also unzip the models manually into the correct xVASynth folder (xVASynth\resources\app\models\skyrim). Once the extraction is complete, you can delete the zipped voice model files.  
	  
	</details>


4. Download the .lip plugin for xVASynth [here](https://www.nexusmods.com/skyrimspecialedition/mods/55605) and download FaceFXWrapper from [here](https://www.nexusmods.com/skyrimspecialedition/mods/20061) (you do not need to download CK64Fixes). Instructions on how to install these are on the .lip plugin Nexus page. Make sure to place FaceFXWrapper in the plugins folder as stated on the .lip plugin page.

5. Download the Elder Scrolls pronunciation dictionary from [here](https://www.nexusmods.com/skyrimspecialedition/mods/56778/), and follow the instructions to install.

6. In the xVASynth UI, if "Skyrim" is not already selected, please do so by clicking the arrows symbol in the top left corner. On the navigation bar on the top right of the xVASynth UI, click on the "ae" icon. Once opened, click on the CMUDict dictionary and select "Enable All" in the bottom left corner. Do the same for "xVADict - Elder Scrolls" received from the above step.


## Required Skyrim Mods
**NB:** Always ensure you are downloading the right version of each mod for your version of Skyrim. **This is the #1 reason for installation problems.** You can check your Skyrim version by right-clicking its exe file in your Skyrim folder and going to Properties -> Details -> File version. VR users can just download the VR version of each mod if available, or SE if not.

Please follow the installation instructions on each of the linked pages:

- [SKSE](http://skse.silverlock.org/) (once installed by following the included readme.txt, run SKSE instead of the Skyrim exe. Note that there is a separate VR version of SKSE)
- [VR Address Library for SKSEVR](https://www.nexusmods.com/skyrimspecialedition/mods/58101  )
  or [Address Library for SKSE Plugins](https://www.nexusmods.com/skyrimspecialedition/mods/32444)
- [PapyrusUtil SE]( https://www.nexusmods.com/skyrimspecialedition/mods/13048) (the VR version can be found under "Miscellaneous Files")
- [UIExtensions](https://www.nexusmods.com/skyrimspecialedition/mods/17561) (if using text input instead of mic)


## Optional Skyrim Mods
These mods aren't strictly necessary for Mantella to work, but they do greatly improve the experience.

- [No NPC Greetings](https://www.nexusmods.com/skyrim/mods/746) (recommended so that Mantella voicelines are not interrupted by vanilla voicelines)
- [UIExtensions](https://www.nexusmods.com/skyrimspecialedition/mods/17561) (to use text input instead of mic input)
- [World Encounter Hostility Fix - Performance Version](https://www.nexusmods.com/skyrimspecialedition/mods/91403  ) (stops certain NPCs from turning hostile when you cast the Mantella spell on them). Note that this mod requires the [Unofficial Skyrim Special Edition Patch (USSEP)](https://www.nexusmods.com/skyrimspecialedition/mods/266). Mantella needs to be loaded after USSEP in your load order.


## Language Models (LLMs)
There are a number of different LLMs to choose from, ranging from small local models to expensive externally hosted models. Note that some smaller models may struggle to handle long term conversations and memory summarising. If you just want to get started without thinking too much about it / explore alternative options later and are new to Mantella, you can quickly get started via the OpenAI instructions below (the first month gives you $5 free credits).

### OpenAI (First $5 Free)
Copy your OpenAI secret API key (see [here](https://help.openai.com/en/articles/4936850-where-do-i-find-my-secret-api-key) if you need help finding it (you will need to set up an account if you haven't already) and paste into `MantellaSoftware/GPT_SECRET_KEY.txt`. Do not share this key with anyone. While there is a free trial, you will need to set up your payment details for the API to work.

### OpenRouter (First $1 Free, Free Models Often Available)
Create an account with OpenRouter. Go to the "Keys" tab and generate a new key, saving its value to MantellaSoftware/GPT_SECRET_KEY.txt. Do not share this secret key with anyone. In MantellaSoftware/config.ini, set `model` to a model from the list [here](https://openrouter.ai/docs#models) (eg `undi95/toppy-m-7b`). Set `alternative_openai_api_base` to "https://openrouter.ai/api/v1" (without quotes).

### text-generation-webui (Free Local Models)
Install text-generation-webui from [here](https://github.com/oobabooga/text-generation-webui). Place a local model into the `text-generation-webui\models folder` (to get started, you can download `toppy-m-7b.Q4_K_S.gguf` from [here](https://huggingface.co/TheBloke/Toppy-M-7B-GGUF/tree/main?not-for-all-audiences=true)). Paste the text "--extensions openai --auto-launch" (as well as "--cpu" for CPU users) into the installed folder's CMD_FLAGS.txt file. Start text-generation-webui and wait for the UI to open in your web browser. Navigate to the "Model" tab, select your model from the drop-down list, and click "Load". In your `MantellaSoftware/config.ini` file, set `alternative_openai_api_base` to "http://127.0.0.1:5000/v1" (without quotes). Just to note, you need to make sure text-generation-webui is running when running Mantella!

### koboldcpp (Free Local Models)
Install koboldcpp's latest release from here: https://github.com/LostRuins/koboldcpp/releases.  If you have a nvidia gpu with cuda support, download the koboldcpp.exe file.  If you do not or do not want to use cuda support, download the koboldcpp_nocuda.exe.  Download it outside of your skyrim, xvasynth or mantella folders.  Download a local large language model, such as `toppy-m-7b.Q4_K_S.gguf` from [here](https://huggingface.co/TheBloke/Toppy-M-7B-GGUF/tree/main?not-for-all-audiences=true)).  Save that somewhere you can easily find it, again outside of skyrim, xvasynth, or mantella.  Run the koboldcpp.exe.  When presented with the launch window, drag the "Context Size" slider to 4096.  Click the "Browse" button next to the "Model:" field and select the model you downloaded.  Under the presets drop down at the top, choose either Use CLBlas, or Use CuBlas (if using Cuda).  You will then see a field for GPU Layers. If you want to use CPU only leave it at 0.  If you want to use your GPU, you can experiement with how many "layers" to offload to your GPU based on your system.  Then click "Launch" in the bottom right corner.  In your `MantellaSoftware/config.ini` file, set `alternative_openai_api_base` to "http://localhost:5001/v1" (without quotes).  Just to note, you need to make sure koboldcpp is running when running Mantella!

### koboldcpp Google Colab Notebook (Free Cloud Service, Potentially Spotty Access / Availablity)
This option does not require a powerful computer to run a large language model, because it runs in the google cloud.  It is free and easy to use, and can handle most .gguf models that are up to 13B parameters with Q4_K_M quantization all on the free T4 GPU you get with google colab.  The downside is Google controls dynamically when the GPUs are available and could throttle your access at any time, so it may not always work / be available.  To use this method, go to this web page: https://colab.research.google.com/github/LostRuins/koboldcpp/blob/concedo/colab.ipynb.  Click the play button that appears below the text "Enter your model below and then click this to start Koboldcpp."  Wait until text stops generating (probably will take a minute or two).  You should see a URL link near the end of the text after a statement like "Connect to the link below," with a silly name, in a format like https://its-taking-time-indeed.trycloudflare.com.  You may want to click on the link just to ensure koboldcpp pops up to ensure its ready before proceeding.  Select that link and copy it with CTRL+C.  In your `MantellaSoftware/config.ini` file, set `alternative_openai_api_base` to that URL by pasting it, and then add /v1 at the end. So it will look something like alternative_openai_api_base = https://its-taking-time-indeed.trycloudflare.com/v1.  Make sure to keep your browser open to the koboldcpp colab notebook while using Mantella so it does not turn off.  If you want to choose a different llm model to use with this method, make sure it is a .gguf model and follow the instructions on the colab to do so.  Be sure to close your browser tab once you're finished your Mantella session, to free up the GPU and help avoid hitting Google's usage limits.

### Other Services
Mantella has the ability to support other language model services, although these services do need to support outputs in the OpenAI format (like text-generation-webui does via the "--extensions openai" option above).


## Setup & Configuration
1. Set up the MantellaSoftware/config.ini file with your paths to Skyrim (`skyrim_folder`), xVASynth (`xvasynth_folder`), and the Mantella Skyrim mod (`mod_folder`). If you are using a Wabbajack modlist, you may need to try searching for a folder called overwrite/root or "Stock Game" in your Mod Organizer 2 / Wabbajack installation path and set this as your `skyrim_folder` path. For FUS users, once you set this path and cast the spell once, you then need to set your `skyrim_folder` path back to your actual Skyrim folder. If you are using Mod Organizer 2, you can find the mod folder by right clicking the mod in the Mod Organizer 2 UI and selecting "Open in Explorer". If you are instead using Vortex, you need to point mod_folder to your Skyrim/Data folder. So Vortex users essentially need to take the Skyrim folder path they have set in `skyrim_folder` and add "\Data" to the end of it.

2. Run Mantella.exe by double-clicking it (ie not by running through Mod Organizer 2 / Vortex as it will not work), wait for the message "Waiting for player to select an NPC..." to display. Once it does, it is ready for you to select an NPC in-game via the Mantella spell.

3. When you first load the mod, MAKE SURE TO CREATE A SAVE AND RELOAD THAT SAVE. The voicelines will not play otherwise! I learned this the hard way. You do not have to create a new game to do this, you can also create a new save in an existing game. While there have not been issues reported with using Mantella in an existing save so far, please be aware that adding mods mid-game can cause problems.

4. The Mantella spell & power should be added to your inventory under the Illusion category in the Magic menu once you install the mod. Conversations can be started by selecting an NPC with the spell, power, or hotkey (default is H). You can end a conversation by casting the Mantella End Conversation spell, or by simply saying / typing "goodbye". If the NPC responds with "safe travels" then the conversation has ended correctly via this latter method. If the NPC is unavailable to the mod, the message "Conversation ended." should immediately pop up in the top left corner and the conversation will exit. If the only message you see from the spell is "Conversation ended", please refer to the "Issues Q&A" section for common solutions to this.

5. Many options can be tweaked in the Mantella MCM, such as NPC actions and radiant conversations.

6. Voicelines are cached in the MantellaSoftware/data/voicelines/ folder. If this data takes up too much space over time, the contents of voicelines/ can be periodically deleted.

7. If you are experiencing errors, please see the issues Q&A below. Otherwise, please share the details of the errors and your MantellaSoftware/logging.log file on the Mantella Discord [#issues channel](https://discord.gg/Q4BJAdtGUE). You can also try enabling debugging in `MantellaSoftware/config.ini`. This allows Mantella.exe to run without Skyrim needing to be open. There are a few extra options in the debugging section to play around with which are applied when the debugging option is enabled.
