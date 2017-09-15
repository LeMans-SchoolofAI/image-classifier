https://codelabs.developers.google.com/codelabs/tensorflow-for-poets

git clone https://github.com/googlecodelabs/tensorflow-for-poets-2
cd tensorflow-for-poets-2

//subfolder 
tf_files/convbattle/converse
tf_files/convbattle/newbalance

set IMAGE_SIZE=224
set ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"

//not installed
tensorboard --logdir tf_files/training_summaries &

python -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=500 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=tf_files/convbattle


// windows exec
// training
python -m scripts.retrain --image_dir=tf_files\convbattle\ --bottleneck_dir=tf_files\bottlenecks --how_many_training_steps=500 --model_dir=tf_files\models\ --summaries_dir=tf_files\training_summaries\mobilenet_0.50_224 --output_graph=tf_files\retrained_graph.pb --output_labels=tf_files\retrained_labels.txt --architecture=mobilenet_0.50_224 

// classifying
python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\converse\converse0067.jpg
converse 1.0
newbalance 1.58378e-15

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\converse\converse0183.jpg
converse 1.0  +++++
newbalance 3.87269e-11

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\converse\conversepinterest117.jpg
converse 0.999458
newbalance 0.000541785

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\converse\conversepinterest408.jpg
converse 0.998
newbalance 0.00200032


python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalance0093.jpg
newbalance 1.0
converse 1.55583e-12

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalance0153.jpg
newbalance 0.996189
converse 0.00381084

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalancepinterest015.jpg
converse 0.997756
newbalance 0.00224402

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalancepinterest019.jpg
converse 1.0
newbalance 1.58692e-13

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalancepinterest040.jpg
converse 0.764252     ///!\\\
newbalance 0.235748

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalancepinterest055.jpg
newbalance 0.993334
converse 0.0066659

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalancepinterest108.jpg
newbalance 0.956941
converse 0.0430587

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalancepinterest206.jpg
converse 0.503913 ++++
newbalance 0.496087

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalancepinterest293.jpg
converse 0.712977 ///!\\\
newbalance 0.287023

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\convbattle\newbalance\newbalancepinterest734.jpg
newbalance 1.0
converse 5.80706e-10

//validation
python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\newbalance\newbalancezappos036.jpg
converse 0.999688 ///!\\\ VANS
newbalance 0.000312086

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\newbalance\newbalancezappos050.jpg
newbalance 0.999984
converse 1.64491e-05

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\newbalance\newbalancezappos133.jpg
converse 0.999963 ///!\\\
newbalance 3.74078e-05

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\newbalance\newbalancezappos149.jpg
newbalance 0.998362
converse 0.0016385

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\newbalance\newbalancezappos274.jpg
converse 0.918787 ///!\\\
newbalance 0.0812129

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\newbalance\newbalancezappos356.jpg
converse 0.990361 ///!\\\
newbalance 0.00963913

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\newbalance\newbalancezappos488.jpg
newbalance 0.975009
converse 0.0249914

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\converse\conversezappos004.jpg
converse 1.0
newbalance 1.17533e-07

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\converse\conversezappos035.jpg
converse 0.999993
newbalance 6.69295e-06

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\converse\conversezappos172.jpg
converse 1.0
newbalance 8.41235e-13

python -m scripts.label_image --graph=tf_files\retrained_graph.pb --image=tf_files\validation\converse\conversezappos742.jpg
converse 1.0
newbalance 2.26652e-08