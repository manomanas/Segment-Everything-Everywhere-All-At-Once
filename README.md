# 👀*SEEM:* Segment Everything Everywhere All at Once
:apple:\[[Demo Route 1](https://36771ee9c49a4631.gradio.app)\]  :orange:\[[Demo Route 2](https://4a489753d0c824e0.gradio.app)\]     :kiwi_fruit:\[[Demo Route 3](https://8c52faee5271add1.gradio.app)\]   :grapes:\[[ArXiv](https://arxiv.org/pdf/2304.06718.pdf)\]

We introduce **SEEM** that can **S**egment **E**verything **E**verywhere with **M**ulti-modal prompts all at once. SEEM allows users to easily segment an image using prompts of different types including visual prompts (points, marks, boxes, scribbles and image segments) and language prompts (text and audio), etc. It can also work with any combinations of prompts or generalize to custom prompts!

## :bulb: Highlights

Inspired by the appealing universal interface in LLMs, we are advocating universal, interactive multi-modal interface for any types of segmentation with **ONE SINGLE MODEL**. We emphasize **4** important features of **SEEM** below.
1. **Versatility**: work with various types of prompts, for example, clicks, boxes, polygons, scribbles, texts, and referring image;
2. **Compositionaliy**: deal with any compositions of prompts;
3. **Interactivity**: interact with user in multi-rounds, thanks to the memory prompt of **SEEM** to store the session history;
4. **Semantic awareness**: give a semantic label to any predicted mask;


![SEEM design](assets/teaser.png?raw=true)
A breif introduction of all the generic and interactive segmentation tasks we can do. Try our demo at 
[[Demo Route 1](https://36771ee9c49a4631.gradio.app)\]  [[Demo Route 2](https://4a489753d0c824e0.gradio.app)\]    [[Demo Route 3](https://8c52faee5271add1.gradio.app)\].
## 🔥How to use the demo
- Upload an image;
- Select at least one type of prompt you want (If you want to use referred region of another image please check "Example" and upload another image in referring image panel);
- Remember to give prompt for each promt type you select or there will be an error (Rember to draw on referred image if you use it);
- Click "Submit" and wait for a few seconds.
## 🔥Click, scribble to mask
With a simple click or stoke from the user, we can generate the masks and the corresponding category labels for it.

![SEEM design](assets/click.png?raw=true)
## 🔥Text to mask
SEEM can generate the mask with text input from the user, providing multi-modality interaction with human.

![example](assets/text.png?raw=true)
<!-- 
<div  align="center">    
<img src="assets/text.png" width = "700" alt="assets/text.png" align=center />
</div> -->

## 🔥Referring image to mask
With a simple click or stroke on the referring image, the model is able to segment the objects with similar semantics on the target images.
![example](assets/ref_seg.png?raw=true)

SEEM understands the spatial relationship very well. Look at the three zebras! The segmented zebras have similar positions with the referred zeras. For example, when the left most zebra is referred on the upper row, the left most zebra on the bottom row is segmented.
![example](assets/spatial_relation.png?raw=true)

SEEM understands the oil pastel paintings painted by :chipmunk:
![Picture1](https://user-images.githubusercontent.com/11957155/231908924-c8f46ee4-e3e9-4457-a860-f46716ae5c9a.png)

## 🔥Referring image to video mask
No training on video data needed, SEEM works perfectly for you to segment videos with whatever queries you specify!
![example](assets/referring_video_visualize.png?raw=true)

## 🔥Audio to mask
We use Whiper to turn audio into text prompt to segment the object. Try it in our demo!

<div  align="center">    
<img src="assets/audio.png" width = "900" alt="assets/audio.png" align=center />
</div>

<!-- ## 🔥Combination of different prompts to mask -->

## 🔥Examples of different styles
An example of segmenting a meme.
<div  align="center">    
<img src="assets/emoj.png" width = "500" alt="assets/emoj.png" align=center />
</div>

An example of segmenting a minecraft image.
<div  align="center">    
<img src="assets/minecraft.png" width = "700" alt="assets/minecraft.png" align=center />
</div>
<!-- ![example](assets/minecraft.png?raw=true) -->
An example of using referring image on a popular teddy bear.

![example](assets/fox_v2.png?raw=true)
## Model
![SEEM design](assets/model.png?raw=true)

## Comparison with SAM
In the following figure, we compare the levels of interaction and semantics of three segmentation tasks (edge detection, open-set, and interactive segmentation). Open-set Segmentation usually requires a high level of semantics and does not require interaction. Compared with [SAM](https://arxiv.org/abs/2304.02643), SEEM covers a larger range in both interaction and semantics levels.  For example, SAM only supports limited interaction types like points and boxes, while misses high-semantic tasks since it does not output semantic labels itself. The reasons are: First, SEEM has a unified prompt encoder that encodes all visual and language prompts into a joint representation space. In consequence, SEEM can support more general usages. It has potential to extend to custom prompts. Second, SEEM works very well on text to mask (grounding segmentation) and outputs semantic-aware predictions.
<div  align="center">    
<img src="assets/compare.jpg" width = "500" alt="assets/compare.jpg" align=center />
</div>
<!-- This figure shows a comparison of our model with concurrent work SAM on the level of interactions and semantics. The x-axis and y-axis denote the level of interaction and semantics, respectively. Three segmentation tasks are shown, including Open-set Segmentation, Edge detection, and Interactive Segmentation. These tasks have different levels of interactions and semantics. For example, Open-set Segmentation usually requires a high level of semantics and does not require interaction. Compared with SAM, our model covers a wider range of interaction and semantics levels. For example, SAM only supports limited interaction types like points and boxes, while misses high-semantic tasks since it does not output semantic labels itself. Note that although we do not report edge detection results, our model can support it by simply converting masks to edges. -->

## :bookmark_tabs: Catelog
- [x] SEEM + Whisper Demo
- [ ] SEEM + Whisper + Stable Diffusion Demo
- [ ] Inference and installation code
- [ ] Hugging Face Demo

## :cupid: Acknowledgements
We thank these wonderful projects:
- [X-Decoder](https://github.com/microsoft/X-Decoder)





<!-- ## Citation (update when paper is available on arxiv)
If you find this project helpful for your research, please consider citing the following BibTeX entry.
```BibTex

``` -->
