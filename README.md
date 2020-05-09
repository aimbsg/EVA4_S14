# EVA4_S14
Custom dataset preparation for the final depth estimation project

Drive link to dataset : https://drive.google.com/open?id=1Hr1OuftLZ0reDac1yJ2wAspwE9gnUQEi
1) bg
2) fg
3) fg_bg
4) fg_bg_mask
5) fg_bg_depth

1) Forest, park, seashore and road. Total images = 100; Channels = RGB; Size = 905KB; Resolution = 224X224
2) Men, Women, Children and combination of men-women, women-children and men-children. Total images = 100; Channels = RGB; Size = 576KB; Resolution = 160X160
3) Randomly placed each fg 40 times(with flips) over each bg. Total images = [100X100X(20X2)] 400K. Channels = RGB; Size = 2.2GB; Resolution = 224X224
4) fg is converted from RGB to black and overlaid on top of black background. This is done along with step 3 (in the same for loop)
5) Tweaks with respect to image input folder and save have been made from the shared Dense Depth code. Have created 40K images because of RAM restrictions. Image loading is done on CPU while prediction is done on GPU. Need to load the data as well in GPU for fast processing.
Total images = 40K
