# Code for Image preprocessing and binary conversion
for thesis

clc;
clear;close all
name=["弹开","Coalescence","拉伸分离","反向分离","小韦伯数融合"];
name_str=char(name);
path='D:\Droplet\WATER\1atm\2025-11-19\';
for i=2:1:2
D = dir(strcat(path,'\PROCESS\',name_str(1,:,i)));
for k=1:length(D)-2
% for k=1:1:1
dirname=['time' num2str(k)];%新的文件夹名
OutputDir = strcat(path,'\PROCESS\',name_str(1,:,i),'\',dirname,'\add1\');  %要保存处理后的图像的文件路径
files = dir(fullfile(path,'\original\',name_str(1,:,i),'\',dirname,'\*.tif')); %要处理的图像路径
lengthFiles = length(files)              %要处理图像的数量
for n=1:lengthFiles
Img = imread(strcat(path,'\original\',name_str(1,:,i),'\',dirname,'\',files(n).name));
% thresh=graythresh(Img); %按照图像寻找阈值
% Img=rgb2gray(Img1)
thresh=0.0625*0.5; %人为控制阈值
Img1=im2double(Img);
Img2=im2bw(Img1,thresh);
imwrite(Img2,[OutputDir,files(n).name]);
end
end
end
