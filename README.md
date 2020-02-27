# F0_IF_model
This is a proposed algorithm to extract voicing decision and pitch from instantaneous frequency of a speech signal
Matalb release MatlabR2018b

List of code file

###### main program ######
F0_VUV_estimation.m

#####  functions   #######
F0_IF_VF.m
HT_fi.m
linsmooth.m
medsmooth.m
###########################


%%%%%%%%%%% Default parameters
% f0min=120; %80 (Male) 120(Female)
% f0max=400; %270 (Male) 400 (Female)
% f0step=0.1;% sweeping step of f0 candidates (from f0min to f0max)
% framedur=32;% in ms
% timestep=10;%in ms
% smoothing_filter=0;%0: median smoothing, 'lin': linear smoothing
% smooth_period=1;% smoothing period in ms

  
%%%%%%%%%%% Default thresholds
% vuv_frame_coef=0.9;     %(or any value between 0.85 and 0.95) Ratio of 
%                          unvoiced points in a frame to take VUV decision

% threshold1=1;           %difference between fi_inst(k) and the highest
%                          multiple of F0_cand(k)

% threshold2=10;          %Maximum of mod(f0_cand2/f0_cand1) to decide
%                          whether f0_cand2 is nearly a multiple of f0_cand1

% dfi_vuv_threshold=1500; %for clean speech (For noisy speech with unknown
%                          SNR, better replace
%                          dfi_vuv_threshold=mean(dfi_value_frame)
%                          in F0_IF_VF.m file)
