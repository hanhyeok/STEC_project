# Pathogenic potential assessment of the Shiga toxin-producing <i>Escherichia coli</i> by a source attribution-considered machine learning model

Hanhyeok Im<sup>a,b</sup>, Seung-Ho Hwang<sup>a,b</sup>, 
Byoung Sik Kim<sup>c</sup>, Sang Ho Choi<sup>a,b,1</sup>

<sup>a</sup> National Research Laboratory of Molecular microbiology and Toxicology<br>
<sup>b</sup> Department of Agricultural Biotechnology and Center for Food Safety and Toxicology, Seoul National University, Seoul 08826, Republic of Korea<br>
<sup>c</sup> Department of Food Science and Engineering, Ewha Womans University, Seoul 03760, Republic of Korea<br>
<sup>1</sup> Correspondence: choish@snu.ac.kr<br>

### Summary 
Here, we developed the model using support vector machine (SVM) algorithm, the SVM model, to predict the 
pathogenicity of Shiga toxin-producing <i>Escherichia coli</i> (STEC) isolates using their WGS data. 
The input dataset for the ML models was generated using distinct gene repertories from
positive (pathogenic) and negative (nonpathogenic) control groups where each STEC isolate was designated
based on the source attribution, the relative risk potential of the isolation sources.
The SVM model successfully predicted the pathogenicity of the isolates from the major sources of STEC outbreaks,
the isolates with the history of outbreaks, and the isolates that cannot be assessed by conventional methods. 
Furthermore, the SVM model effectively differentiated the pathogenic potentials of the isolates at a finer resolution.
These results suggest that the SVM model is reliable and broadly applicable method to evaluate 
the pathogenic potential of STEC isolates.

------------

### Docker - OSX/Linux/Windows/Cloud

We created a docker container which contained the pipeline used in this study. 
To install it:
```
       $ docker pull hanhyeok/stec_prediction
```
The pipeline needs the .gbk file(s) as input data, and we recommend the .gbk file generated by [Prokka](https://github.com/tseemann/prokka) genome annotation program.<br>
To use it, you would use a command such as this (substitute the directory path to yours). If your .gbk files are assumed to be stored in **/home/test** :
```
       $ docker run -it -v /home/test:/data hanhyeok/stec_prediction 
(base) $ conda run -n snakemake snakemake -q --cores N
```
If you run again the pipeline, please remove the **README.md** file at the 'result' folder and run it again.
