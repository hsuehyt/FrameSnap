# FrameSnap

Simple FFmpeg video frame extractor for Windows CMD.

Extract image frames from a video file using FFmpeg.

---

# 1. Install FFmpeg

Open Windows CMD and install FFmpeg with:

```cmd
winget install Gyan.FFmpeg
```

After installation, restart CMD.

Check if FFmpeg is installed correctly:

```cmd
ffmpeg -version
```

---

# 2. Open CMD in the video folder

Place your video file in a folder.

Example:

```text
D:\Videos\
    2026-05-18 23-00-46.mp4
```

Open CMD directly in that folder:

## Method A (Recommended)

1. Open the folder in Windows Explorer
2. Click the address bar
3. Type:

```text
cmd
```

4. Press Enter

CMD will open in the current folder.

---

## Method B

Hold:

```text
Shift + Right Click
```

inside the folder and choose:

```text
Open in Terminal
```

Then type:

```cmd
cmd
```

to switch from PowerShell to CMD.

---

# 3. Create output folder

```cmd
md output
```

This creates a folder named:

```text
output
```

---

# 4. Extract frames

```cmd
ffmpeg -i "2026-05-18 23-00-46.mp4" -vf "fps=1" ./output/frame_%04d.jpg
```

Extracted images will be saved as:

```text
output/frame_0001.jpg
output/frame_0002.jpg
output/frame_0003.jpg
...
```

---

# Command Explanation

## Input video

```cmd
-i "2026-05-18 23-00-46.mp4"
```

Specifies the input video file.

---

## Frame rate extraction

```cmd
-vf "fps=1"
```

Means:

```text
Extract 1 frame per second
```

---

# Change extraction rate

## 1 frame every second

```cmd
-vf "fps=1"
```

---

## 2 frames every second

```cmd
-vf "fps=2"
```

---

## 1 frame every 5 seconds

```cmd
-vf "fps=1/5"
```

---

## 1 frame every 10 seconds

```cmd
-vf "fps=1/10"
```

---

## 30 frames every second

```cmd
-vf "fps=30"
```

---

# Output filename format

```cmd
frame_%04d.jpg
```

Means:

```text
frame_0001.jpg
frame_0002.jpg
frame_0003.jpg
```

`%04d` means 4-digit numbering.

---

# Example

## Extract 1 frame every 5 seconds

```cmd
ffmpeg -i "video.mp4" -vf "fps=1/5" ./output/frame_%04d.jpg
```

---

# Useful Notes

- Supports mp4, mov, mkv and most video formats
- JPG can be replaced with PNG

Example:

```cmd
ffmpeg -i "video.mp4" -vf "fps=1" ./output/frame_%04d.png
```

- Existing files may be overwritten if filenames are the same

---

# FFmpeg

Official website:

https://ffmpeg.org/
