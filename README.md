# faceswap_gl
Face swap using Python + OpenGL

![Demo gif](images/demo.gif)

This implementation finds facial landmarks on both the source and destination images, and  generates a texture to be used on a 3D model of the face. This Model is then positioned over the destination image using the landmarks.

| Source | Destination | Texture | 3D face | Result |
| ------ | ------- | ----------- | ------------------ | ------ |
| ![Source image](images/src.jpg) | ![Destination image](images/dst.png) | ![Texture generated from source image](images/texture.png) | ![Texture applied to 3D model positioned according to the face on the destination image](images/3dface.png) | ![Face swap result](images/result.png) |

## Installation

Clone the repo
```
git clone https://github.com/ibonn/faceswap_gl.git
```

Install required modules
```
cd faceswap_gl/
pip install -r requirements.txt

https://askubuntu.com/questions/492863/install-pygame-in-anaconda

conda install -c https://conda.binstar.org/bri11091 pygame


riehlnm/pygame
bri11091/pygame
```

## Usage

Basic usage
```
python swap.py -s <SRC_PATH> -d <DST_PATH> -o <OUT_PATH>

MESA_LOADER_DRIVER_OVERRIDE=i965 python swap.py -s ../images/kyle.jpg -d ../images/naruto.jpg -o ../images/kyle_naruto.jpg

MESA_LOADER_DRIVER_OVERRIDE=i965 python swap.py -s ../images/samurai.jpg -d ../images/naruto.jpg -o ../images/kyle_naruto.jpg

```

More options:
* **-s/--src**: Path to the source image  
* **-d/--dst**: Path to the destination image/video
* **-o/--output**: Output path
* **-t/--texture**: Size of the texture. The lower the value the faster the program starts (but the source face resolution is lower). Defaults to 256px
* **-b/--border**: Padding size. Not implemented yet
* **-m/--mask**: Output a video with the mask

Example:
```
python swap.py -s tomhanks.jpg -d dicaprio.mp4 -o out.mp4 -t 1024
```
