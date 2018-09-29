# Vegetables identification using Tensowflow

Final Steps for training and optimising(Reference has been taken from Tensorflow for Poets 2)

For setup, installtion and other detals you can refer this link:

https://codelabs.developers.google.com/codelabs/tensorflow-for-poets-2/#0


Sample Image Size:

IMAGE_SIZE=224

Architecture Used: Mobilenet

ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"

## Retraining Script ##
python -m scripts.retrain   --bottleneck_dir=tf_files/bottlenecks   —how_many_training_steps=1000   --model_dir=tf_files/models/   --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}"   --output_graph=tf_files/retrained_graph.pb   --output_labels=tf_files/retrained_labels.txt   --architecture="${ARCHITECTURE}"   --image_dir=tf_files/Images

## Identify Vegetable ##
python -m scripts.label_image --image=../tomato.jpg --graph=tf_files/retrained_graph.pb

Above script will give result like this:

Evaluation time (1-image): 0.294s

Tomato (score=0.90072)

...

