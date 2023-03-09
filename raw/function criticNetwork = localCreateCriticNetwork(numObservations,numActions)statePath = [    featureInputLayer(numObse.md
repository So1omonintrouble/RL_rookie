```matlab
function criticNetwork = localCreateCriticNetwork(numObservations,numActions)
statePath = [
    featureInputLayer(numObservations,'Normalization','none','Name','state')
    fullyConnectedLayer(32,'Name','fc1')];
actionPath = [
    featureInputLayer(numActions,'Normalization','none','Name','action')
    fullyConnectedLayer(32,'Name','fc2')];
commonPath = [
    concatenationLayer(1,2,'Name','concat')
    reluLayer('Name','reluBody1')
    fullyConnectedLayer(32,'Name','fcBody')
    reluLayer('Name','reluBody2')
    fullyConnectedLayer(1,'Name','qvalue')];

criticNetwork = layerGraph();
criticNetwork = addLayers(criticNetwork,statePath);
criticNetwork = addLayers(criticNetwork,actionPath);
criticNetwork = addLayers(criticNetwork,commonPath);

criticNetwork = connectLayers(criticNetwork,'fc1','concat/in1');
criticNetwork = connectLayers(criticNetwork,'fc2','concat/in2');
end
```

