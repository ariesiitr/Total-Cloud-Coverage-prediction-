# Total-Cloud-Coverage-prediction-
<h1>Dataset</h1>
<p>The main aim of this project was with a given dataset, we had to predict the total cloud coverage in the sky for next 30,60,90 and 120 minutes. The dataset for this project was very imbalanced, so we had to first remove the problems in it.</p>
<p>In the csv file, we had two problems.. </p>
<p>i.) For "total cloud cover (%) column", we had some rows with negative value which was unfeasible and some with value -7999 which was also unfeasible as the % can't be negative. And the total quantity of negative values was large and we couldn't just drop every one of them which would have been a huge data loss. Appearence of all negative values except -7999 was non-uniform. And we had no option other than dropping all of them and for -7999, we had an option. -7999 appeared in triplet form wherever it appeared in the csv file. So we replaced -7999 everywhere in a given triplet with the average of value from row just above the triplet and just after the triplet.</p>
<p>ii.) Two columns Precipitation (accumulated) [mm]’ and ‘moisture’ were irrelevant in the dataset as almost all of their values were zero. So we had to just drop them.
We normalized the dataset as well to avoid gradient related issues.</p>
<h1> Model to be used for training </h1>
<p>Next, as we can see the task was to predict in time series and the most suitable model we could use was lstm. So we created one lstm model using Pytorch.</p>
<p>The first layer was lstm layer with n_features=13, n_hidden=40 and n_layers =3. The values obtained by trying different architectures. Then we used one linear layer with ReLU as activation function and then one more linear layer.</p>
