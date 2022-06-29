# tensorflow-dense-warp-catmull-rom
Reimplementation of the dense image warp with catmull rom interpolation instead of bilinear. The use case can be motion reprojection, as the example below shows.

To use, simply import it, and use it the same way you use the bilinear version. It is a drop-in replacement for `tfa.image.dense_image_warp`

example of motion reprojection:

```py
prev_rgb = dense_image_warp.dense_image_warp_catmull(prev_rgb, in_motion)
```

## Result:
The Catmull-Rom interpolation has less artifacts, notably the elongated crosses created by the bilinear are now smoothly reconstructed with rounded edges. This behavior is much more desirable, especially when dealing with fourier reconstructions or neural networks.

![](catmull_vs_bilin.png)
