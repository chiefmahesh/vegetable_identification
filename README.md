# vegetable_identification
Identify Vegetables using Tensowflow

Final Steps for training and optimising(Reference has been taken from Tensorflow for Poets 2)

Sample Image Size: 
IMAGE_SIZE=224
Architecture Used:
ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"

## Retraining Script ##
python -m scripts.retrain   --bottleneck_dir=tf_files/bottlenecks   —how_many_training_steps=1000   --model_dir=tf_files/models/   --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}"   --output_graph=tf_files/retrained_graph.pb   --output_labels=tf_files/retrained_labels.txt   --architecture="${ARCHITECTURE}"   --image_dir=tf_files/Images
