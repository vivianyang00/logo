# TextLogo3K Dataset
This is the text logo dataset proposed in Aesthetic Text Logo Synthesis via Content-aware Layout Inferring (CVPR 2022).
The dataset consists of 3,470 carefully-selected text logo images that are extracted from the posters/covers of the movies, TV series, and comics in Tencent Video. 
We manually annotate the bounding box, pixel-level mask, and category for each character (glyph) in these text logos.
## Structure
```
TextLogo3K
|   README.md
|   logo_titles.txt
└───train
|   |   
|   └───00v79tmuo39v1va
|       |   poster.jpg
|       |   seg.png, logo.png, logo_resized.png, logo_resized_centre.png, elements.png
|       |   coords_seg.npy, coords_det.npy, char_embeds.npy, word_embeds.npy, len.npy    
|   |
|   └───00ijz9hyqla0ug9
|       |   ...
|   
└───test
|   |
|   └───00ijz9hyqla0ug9
|        |   ...
```
where 
(1) `logo_titles.txt` records the title of each data item, and each line is `ID Split Title(simplified Chinese) Title(raw text)`.
(2) `00v79tmuo39v1va` is the ID of one data item.
(3) `poster.jpg` is the poster image.
(4) `seg.png` is the segmentation image of logo, and the first char is pixel vaue is 50, the second 60, the third is 70, ...
(5) `logo.png`, `logo_resized.png` and `logo_resized_centre.png` are the logo images. `elements.png` is the elemental glyph images.
(6) `char_embeds.npy` and `word_embeds.npy` are the character and word embeddings, respectively. They are from [Chinese Word Vectors](https://github.com/Embedding/Chinese-Word-Vectors): Baidu Encyclopedia (Word + Character + Ngram). The downloaed file's name is `sgns.baidubaike.bigram-char`. We used simplified Chinese titles to lookup the embeddings.
(7) `len.npy` is the number of characters in this logo.
(8) `coords_det.npy` are the location of glyphs in the poster image. We only annotate the most centre parts if the glyph has very long strokes. (format: quadrilateral (top-left x and y, top-right x and y, bottom-right x and y, bottom-left x and y)) 
(9) `coords_seg.npy` and `coords_seg_centre.npy` are location of glyphs in the logo images `logo_resized.png` and `logo_resized_centre.png`, respectively. (format: rectangle (left, top, right, bottom))
(10) More details to be found when you read the data and check them yourself.

## Note
This dataset CAN ONLY be used for academic purposes.
## Contact
wangyizhi@pku.edu.cn

