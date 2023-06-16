https://kno.wled.ge/advanced/custom-features/#create-custom-effects

Create custom effects
It is possible to create your own effects and add them to the FX library. The relevant files for that are FX.cpp and FX.h.

Here is a step-by-step guide on how to make your effect:

Take a look at some of the effects in FX.cpp to see how they are implemented!

Add your own routine in FX.cpp starting with: uint16_t WS2812FX::mode_custom

Add to total number of effects in FX.h line 110: #define MODE_COUNT

Add your mode number (ie#define FX_MODE_CUSTOM 110) in FX.h around line 200.

Add your mode around line 400 of FX.h, like so: _mode[FX_MODE_CUSTOM] = &WS2812FX::mode_custom;

Add it to the functions in FX.h around line 600:mode_custom(void),

Give it a name at the bottom (10 modes per line) in JSON_mode_names[]. Wrap your name in quotes just like the others.

Compile, upload and enjoy! Your new effect will automatically be added to the list in the web ui.