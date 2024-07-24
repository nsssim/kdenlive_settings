# kdenlive_settings
kdenlive settings for screen recording 10 FPS, video codec settings so far

# Video settings 

![image](https://github.com/user-attachments/assets/20dc7648-223d-44ae-8683-638dd38d4e58)

# Audio Settings

![image](https://github.com/user-attachments/assets/068d58c8-aa7a-40ba-9237-6de23768e3e5) 

# Other settings 

```
analyse=0x3:0x113:b_adapt=1:b_bias=0:b_pyramid=2:bframes=3:bluray_compat=0:cabac=1:chroma_me=1:chroma_qp_offset=0:constrained_intra=0:cqm=0:deadzone=21,11:deblock=1:0:0:decimate=1:direct=1:fast_pskip=1:interlaced=0:intra_refresh=0:ip_ratio=1.40:keyint=250:lookahead_threads=8:mbtree=1:me=hex:me_range=16:mixed_ref=0:nr=0:open_gop=0:psy=1:psy_rd=1.00:0.00:qcomp=0.60:qpmax=69:qpmin=0:qpstep=4:rc_lookahead=10:ref=1:scenecut=40:sliced_threads=0:subme=2:threads=24:trellis=0:weightb=1:weightp=1
```

![image](https://github.com/user-attachments/assets/3a477177-1440-406d-a2d1-d7d782b1711d)

# Details 
The string provided (aditional parameters) is a detailed configuration for x264 encoding parameters, which can be used with FFmpeg or other tools that support x264. Each parameter controls a specific aspect of video encoding to balance quality, compression, and processing time. Let’s break down each part of the configuration:

### **General Parameters**

- **`analyse=0x3:0x113`**: Specifies motion estimation algorithms. `0x3` is for macroblock types and `0x113` for motion vector prediction. These settings influence the quality and efficiency of motion estimation.

- **`b_adapt=1`**: Enables adaptive B-frame placement, allowing the encoder to optimize the placement of B-frames for better compression.

- **`b_bias=0`**: Sets the bias for B-frame placement. A value of `0` means no bias; the encoder will not favor or disfavor B-frames.

- **`b_pyramid=2`**: Enables B-frame pyramid mode, allowing B-frames to reference other B-frames. This can improve compression but may increase encoding complexity.

- **`bframes=3`**: Limits the number of consecutive B-frames. `3` means up to three B-frames can be used between I-frames and P-frames.

- **`bluray_compat=0`**: Disables Blu-ray compatibility features. Set to `1` to comply with Blu-ray standards.

- **`cabac=1`**: Enables Context-Adaptive Binary Arithmetic Coding, which improves compression efficiency compared to CAVLC.

- **`chroma_me=1`**: Enables motion estimation for chroma channels. This improves quality, especially for videos with rich color detail.

- **`chroma_qp_offset=0`**: Sets the quantization parameter offset for chroma (color) channels. `0` means no offset, so chroma and luma quantization levels are the same.

- **`constrained_intra=0`**: Disables constrained intra prediction, which restricts intra-frame prediction to areas without inter-frame references.

- **`cqm=0`**: Disables custom quantization matrices, using default matrices for quantization.

- **`deadzone=21,11`**: Defines the quantization deadzone for luma and chroma channels. This affects the level of quantization noise reduction.

- **`deblock=1:0:0`**: Enables the deblocking filter. The `1` means the filter is active, and `0:0` sets the strength of the filter.

- **`decimate=1`**: Enables frame decimation, which reduces the number of frames and helps in compression.

- **`direct=1`**: Sets the direct prediction mode, influencing motion estimation efficiency.

- **`fast_pskip=1`**: Enables fast p-skip mode, optimizing encoding speed at the potential cost of quality.

- **`interlaced=0`**: Indicates that the video is not interlaced. If set to `1`, the encoder would treat the video as interlaced.

- **`intra_refresh=0`**: Disables intra-refresh, which periodically updates the entire frame instead of just macroblocks.

- **`ip_ratio=1.40`**: Sets the ratio of quantization for I-frames compared to P-frames. `1.40` means I-frames are more compressed than P-frames.

- **`keyint=250`**: Defines the maximum interval between keyframes (I-frames). `250` frames between I-frames, which can improve compression but make seeking less precise.

- **`lookahead_threads=8`**: Sets the number of threads for lookahead processing, improving decision-making for frame encoding.

- **`mbtree=1`**: Enables macroblock tree rate control, improving quality and compression by predicting future frames.

- **`me=hex`**: Specifies the motion estimation method as hexagon (hex). A common method for motion estimation.

- **`me_range=16`**: Defines the range of motion estimation. `16` pixels in each direction.

- **`mixed_ref=0`**: Disables mixed reference frames, which could otherwise use different frame types for references.

- **`nr=0`**: Disables noise reduction, keeping details in the video but potentially increasing noise.

- **`open_gop=0`**: Disables open GOP. Closed GOPs are used, meaning each GOP starts with a keyframe.

- **`psy=1`**: Enables psychovisual optimizations, which adjust quantization to improve visual quality.

- **`psy_rd=1.00:0.00`**: Sets the strength of psychovisual optimizations for luma and chroma. `1.00` for luma and `0.00` for chroma.

- **`qcomp=0.60`**: Controls the quantization curve compression. `0.60` strikes a balance between quality and compression.

- **`qpmax=69`**: Sets the maximum quantizer parameter value. Higher values allow for more aggressive compression.

- **`qpmin=0`**: Sets the minimum quantizer parameter value. Lower values maintain higher quality.

- **`qpstep=4`**: Defines the step size for adjusting quantizer parameters.

- **`rc_lookahead=10`**: Sets the number of frames to look ahead for rate control, helping in making better bit allocation decisions.

- **`ref=1`**: Specifies the number of reference frames used. `1` means only one reference frame, which reduces complexity.

- **`scenecut=40`**: Sets the threshold for scene cuts. `40` means the encoder will insert a keyframe if there is a scene change detected above this threshold.

- **`sliced_threads=0`**: Disables multi-threaded encoding using slices, which can improve performance but is not used in this setting.

- **`subme=2`**: Defines the subpixel motion estimation quality. `2` offers a balance between accuracy and computational expense.

- **`threads=24`**: Sets the number of threads used for encoding. `24` threads can speed up encoding on multi-core processors.

- **`trellis=0`**: Disables trellis quantization, which can improve quality but increases encoding time.

- **`weightb=1`**: Enables weighted prediction for B-frames, improving compression.

- **`weightp=1`**: Enables weighted prediction for P-frames.

### Note

These settings provide a detailed configuration for x264 encoding, influencing various aspects of quality, compression, and performance. They balance quality and efficiency while catering to specific encoding needs. Adjust these parameters based on your requirements for video quality, file size, and encoding speed.
