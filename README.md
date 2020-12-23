## Environmental_Audio_Analysis:

### Introduction:
<p align="justify">
130 audio files of length 10 seconds containing sounds in three different acoustic scenes (Airport, park and town-square) across different European cities were analysed for their similarity relationships. Ten different classes were monitored to compare similarity between different files, sub comparisons were also made based on same acoustic scene and classes sets to better understand pattern and relationships.
Ten classes used are: siren, adults_talking, children_voices, announcement speech, announcement _jingle, birds singing, traffic noise, music, footsteps, dog_barking.
Assumptions: Files were annotated correctly, librosa library is stable to use.
</p>

### Annotation process:
<p align="justify">
130 audio files of 10 seconds in three different acoustic scenes (Airport, park and town-square) were annotated. There were
multiple classes present in each file. Annotation tool was simple and straight-forward to use and it was good to have buttons for frequent classes to tag. To make it 
simpler I believe a feature of dynamic range control can be introduced in annotation tool, because there are lot of sounds mainly some background children noise or music which were there and left unnoticed due to less energy, hence using dynamic range control we can increase their impact and notice them to do the right tagging of overall file.

### Dataset Statistics (Fig 1 and Table 1):
![image](https://user-images.githubusercontent.com/42828760/102979428-b8f73700-450e-11eb-976e-e9597f4d4b84.png)
![image](https://user-images.githubusercontent.com/42828760/102981556-cc57d180-4511-11eb-84ad-f4205d8803af.png)

</p>


### Audio Analysis:
<p align="justify">
The utilized Spectro-temporal features are log mel-band energies, extracted from short frames of 10 second audio. These features has been shown to perform well in various audio tagging, sound analysis and sound detection tasks [1,2,3]. Typical value of amount of FFT points chosen for 48 kHz, is 1024, with 50% overlap(512 fft points) using hamming window resulting in total of 938 frames. Using the approach of 50% overlap helps to obtain much clear spectrum as it take data from centre of signal frames. 40 log mel-band energy features were extracted from the magnitude spectrum. Librosa library was used in the feature extraction process.
Keeping in mind that human everyday sounds and environment sounds like bird singing are often contained in a relatively small portion of the frequency range (mostly around 2-8 kHz), extracting features in that range seems like a good approach which deciding for no of mel-bands. Calculated features were aggregated into a single vector over time as mean and standard deviation.Similarity matrix obtained by calculating cosine similarity between 130 files is shown as heat map in Fig 2. As we can see in from Fig 2., the cross-sectional part containing files from 64 to 80(Both x and y axis) and 125 to 129(Both x axis and y axis) is quite dark. Hence, this represents that these set of files are quite similar. Majority of these sub-sections of files has airport and park as their acoustic environment. Common classes that occur in these files in major percentage are adults_talking, footsteps and bird_singing. Files 42, 115 in Fig 2. seems too much uncorrelated with other files as they form a straight white strip (Can be seen on x-axis). Both these files are from paris-airport acoustic environment. These two files seems to form a outlier pattern.
Table 2. shows the average similarity value obtained for each class. It can be seen that classes “footsteps”, “birds_singing”, “traffic_noise”, “siren” , “announcement speech” and “music” have higher value than average similarity. Number of files with classes  “traffic_noise”, “siren” , “announcement speech” and “music” are quite low, maybe that’s why there average similarity values are high.
While doing annotations the sounds from classes “footsteps”, “bird_singing” and “adults_talking” are quite common. From Table 2. we also can see higher average similarity for these classes. Combining the observations from Similarity matrix and Table 2., we can say that these classes form some similarity pattern. 

### Similarity Matrix(Fig 2.):
![image](https://user-images.githubusercontent.com/42828760/102980648-8ea67900-4510-11eb-8301-2540a12c4ef5.png)

### Average Similarity per class(Table 2.):
![image](https://user-images.githubusercontent.com/42828760/102980930-f6f55a80-4510-11eb-9c92-06b88e5f5c44.png)

### Acoustic Environment Similarity(Table 3.):
![image](https://user-images.githubusercontent.com/42828760/102981173-46d42180-4511-11eb-889e-e23eb7fbe3ed.png)

Table 3. shows the average similarity of acoustic patterns present. It is observed that the airport acoustics has the highest average similarity and quite comparable to park acoustics.By observing annotated data[4], it is noticed that adults talking, footsteps occur more together and have same environment as airport in many files. From all the observations it can be concluded that the files with Airport environment and adults_talking, footsteps as a combination forms quite a similar patterns.

### Conclusion:
In this work, we did similarity analysis of audio files. The method using cosine similarity to compare files gave a good start to analyse similarity and which sections of classes are creating most impact. The further analysis by doing similarity comparisons of acoustic scenes as well looking at set of classes which appear together in more similar files helped to gain more insights over similarity pattern. The analysis concluded that files with Airport environment and adults_talking, footsteps combination formed the most similar patterns.

### References:

[1] E. Cakir, T. Heittola, H. Huttunen, and T. Virtanen, “Polyphonic sound event detection using multi-label deep neural networks,” in IEEE International Joint Conference on Neural Networks (IJCNN), 2015.
[2] “Detection and classification of acoustic scenes and events (DCASE),” 2016. [Online]. Available:http://www.cs.tut.fi/sgn/arg/dcase2016/tasksound-event-detection-in-real-life-audio.
 [3] E. Cakir, G. Parascandolo, T. Heittola, H. Huttunen, and T. Virtanen, “Convolutional recurrent neural networks for polyphonic sound event detection,” in IEEE/ACM TASLP Special Issue on Sound Scene and Event Analysis, 2017, accepted for publication.
[4] https://drive.google.com/file/d/18pXzgUybVgfW8qzFopRvtCXj97me5G0w/view?usp=sharing



</p>

