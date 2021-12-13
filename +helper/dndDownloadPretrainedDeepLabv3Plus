function model = dndDownloadPretrainedDeepLabv3Plus(basePath)
% The downloadPretrainedDeepLabv3Plus function loads a pretrained
% DeepLabv3Plus network.
%
% Copyright 2021 The MathWorks, Inc.

dataPath = basePath;
modelName = 'deepLabV3Plus-voc';
netFileFullPath = fullfile(dataPath, modelName + '.zip');
weightsFile = fullfile(dataPath, modelName + '.mat');

if ~exist(netFileFull,'file')
    fprintf('Downloading pretrained '+ modelName +' network.\n');
    fprintf('This can take several minutes to download...\n');
    url = 'https://ssd.mathworks.com/supportfiles/vision/deeplearning/models/deepLabV3Plus/deepLabV3Plus-voc.zip';
    websave (netFileFullPath,url);
    unzip(netFileFullPath, dataPath);
    model = load(fullfile(dataPath, 'deepLabV3Plus-voc.mat'));
else
    fprintf('Pretrained DeepLabv3Plus network already exists.\n\n');
    if exist(weightsFile, 'file')
        model = load(weightsFile);
    else
        unzip(netFileFullPath, dataPath);
        model = load(weightsFile);
    end
end
end
