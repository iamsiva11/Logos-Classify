#Up and running the code for Tensorflow


1/ sudo docker run -it -v $HOME/tf_files/logo-dir/:/tf_files gcr.io/tensorflow/tensorflow:latest-devel

ls /tf_files/logo-data/data-logo

(Optional)

2/ Inside the container
cd /tensorflow
git pull

3/ python tensorflow/examples/image_retraining/retrain.py \
--bottleneck_dir=/tf_files/bottlenecks \
--how_many_training_steps 4000 \
--model_dir=/tf_files/inception \
--output_graph=/tf_files/retrained_graph.pb \
--output_labels=/tf_files/retrained_labels.txt \
--image_dir /tf_files/logo-data/data-logo/	


<Training Image>

<Training Finished Image>


4/ curl -L https://goo.gl/tx3dqg > $HOME/tf_files/logo-dir/label_image.py

5/ Restart Docker image:
sudo docker run -it -v $HOME/tf_files/logo-dir/:/tf_files gcr.io/tensorflow/tensorflow:latest-devel

6/ Predict/Test :
python /tf_files/label_image.py /tf_files/logo-data/data-logo/adidas/pic_005.jpg

python /tf_files/label_image.py /tf_files/logo-data/data-logo/adidas/pic_005.jpg

python /tf_files/label_image.py /tf_files/logo-data/data-logo/nike/pic_005.jpg
<Img>

python /tf_files/label_image.py /tf_files/logo-data/data-logo/puma/pic_005.jpg
<Img>








