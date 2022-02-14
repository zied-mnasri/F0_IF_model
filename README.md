### F0_IF_model ###
This is a proposed algorithm to extract voicing decision and pitch from instantaneous frequency of a speech signal

Matlab release R2020

List of code file

###### main program ######
F0_IF_Matlab_Compare.m

#####  functions   #######
F0_IF_VF.m

HT_fi.m

linsmooth.m

medsmooth.m

fi_extract.m

######List of audio and ground truth f0 files #######

###### Audio files (for test) ########

mic_F01_sa1.wav (female voice)

mic_M01_sa1.wav (male voice)

####### f0 ground trouth files #######

ref_F01_sa1.f0 (for female voice)

ref_M01_sa1.f0 (for male voice)

%%%%%%%%% Defaults parameters for F0_IF_VF.m %%%%%%%%%%%%%%

f0min=120; %80 (Male) 120(Female)

f0max=400; %270 (Male) 400 (Female)

f0step=0.05;% sweeping step of f0 candidates (from f0min to f0max)

framedur=25;% in ms

timestep=10;%in ms

smoothing_filter=1;%1: median smoothing, 2: linear smoothing

smoothing_dur=0.5;% smoothing period in ms
  
%%%%%%%%%%% Default thresholds (for F0_IF_VF.m) %%%%%%%%%%%

vuv_frame_coef=0.9;     %(or any value between 0.85 and 0.95) Ratio of 

                        % unvoiced points in a frame to take VUV decision

threshold1=1;           %difference between fi_inst(k) and the highest
                        
                        % multiple of F0_cand(k)

threshold2=10;          %Maximum of mod(f0_cand2/f0_cand1) to decide
                        
                        %whether f0_cand2 is nearly a multiple of f0_cand1

 dfi_vuv_threshold=1500; % for clean speech: 1500 for female, 1000 for male voicefor clean speech 
                        
                        %(For noisy speech with unknown SNR, better replace dfi_vuv_threshold=mean(dfi_value_frame)
                        
                        %in F0_IF_VF.m file)

%%%%%%%%%%% Default parameters for MATLAB built-in function (pitch) used for benchmarking %%%%%%%%%%%

hr_threshold=0.5; %Harmonic ratio for Matlab built-in function (pitch)

Method='SRH';

WindowLength=framedur*fs/1000; %framedur and timestep are the same mentioned above

OverlapLength=timestep*fs/1000;

Range=[f0min,f0max; %same boundary values for both methods

MedianFilterLength=smoothing_dur*fs/1000); %Sampling frequency (fs) is obtained by Matlab function audioread

%%%%%%%%%%%%%%% Notice about citation %%%%%%%%%%%%%%%%%%%
If you use this code for academic research, please cite it as follows:

Mnasri, Zied, Stefano Rovetta, and Francesco Masulli. "A Novel Pitch Detection Algorithm Based On Instantaneous Frequency." 2021 29th European Signal Processing Conference (EUSIPCO). IEEE, 2021.

Bibtex
@inproceedings{mnasri2021novel,
  title={A Novel Pitch Detection Algorithm Based On Instantaneous Frequency},
  author={Mnasri, Zied and Rovetta, Stefano and Masulli, Francesco},
  booktitle={2021 29th European Signal Processing Conference (EUSIPCO)},
  pages={16--20},
  year={2021},
  organization={IEEE}
}
