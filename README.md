# tm-drum-recognition
A Teachable machine project to recognize particular drum sounds

# main instuments
I tried importing drum samples from my library. But since Teachable Machine doesn't allow custom samples, all of the sound were recorded by mouth, including:
- Drums (26 samples, with length variance to improve accuracy)
- Snare (20 samples, with length variance to improve accuracy)
- Clap (13 actual hand claps)
- Hi Hats (22 samples, 10 of which contain hi-hat patterns aka multiple hi-hat instances)
- Background noise (for calibrating the model)

# How it works
Teachable machine is mostly about image recognition. As a result, the recorded sounds were converted to spectrogram form in order for it to work. This may lead to conflict as some sounds are found in the same frequency range and may have similar lenght

# Results
Detect confidence for each types (best-case scenario):

Background noise:

![image](https://user-images.githubusercontent.com/85775157/164004169-0be4bf78-7549-416e-9fe0-2d35aae5cf3f.png)

Kick:

![image](https://user-images.githubusercontent.com/85775157/164004426-cae32460-06e8-4eef-a5ee-18452343d64f.png)

Snare:

![image](https://user-images.githubusercontent.com/85775157/164005413-7b975973-f64d-40cd-9060-0ec1182daccf.png)

Clap:

![image](https://user-images.githubusercontent.com/85775157/164005775-7c84c464-df6a-4cb6-a641-60c2977e6ee5.png)


Hi-hats:

![image](https://user-images.githubusercontent.com/85775157/164005643-70427a7d-477b-43bd-874d-b9e4a469a3cb.png)

# Problems
- Most of the time the model is confused between clap and snare samples.
- Hi-hats are mostly recognized when played in a repeating pattern, when played separatedly it was identified as a clap due to short length and being at a similar frequency in the speactrum.

# Application
Although this model is used to identify sounds, a new GAN model can be trained to imitate the spectrogram of the abovementioned percussions, then that spectrogram can be converted back to sound format, creating new drums sounds. This will be a great tool for electronic musicians who need new sounds to experiment with.
