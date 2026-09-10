# Feature Scaling

 the logic of certain algorithms of ML models are created in such a way that utilizes
 distance between the two points. so to avoid the influence of a feature with higher numeric value.
 we simply scale the data to bring all the features in common footing and make thier influence comparable.
 it is the  last step of the data processing pipeline. 

there are two dominant techniques of feature scaling:

Standardization (Z-score scaling):
centers data at mean 0, scales to std deviation =  1.
output is unbounded — no fixed min/max.
assumes (or at least behaves best with) roughly Gaussian-shaped data.
preferred for: linear regression, logistic regression, PCA, SVM (RBF kernel), anything relying on variance/covariance structure.

Normalization (Min-Max scaling)
compresses data into a fixed range, typically [0,1]
highly sensitive to outliers — one extreme value stretches the range and squashes everything else together.
preferred for: algorithms needing bounded input (neural net activations, image pixels), or when there's no distributional assumption to lean on.

Important exception: tree-based models (decision trees, random forests, gradient boosting) split on thresholds, not distances or gradients — they're scale-invariant. Scaling them is wasted effort.