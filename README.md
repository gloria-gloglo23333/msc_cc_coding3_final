# msc_cc_coding3_final




https://user-images.githubusercontent.com/73170220/174462388-5d2ec869-3975-4aea-b9a1-6cfceb98f9ad.mp4



### For this final project, I chose to use machine learning to generate music. I used a model called Melody RNN, a recurrent neural network developed by Google in magenta, as my main generative model. Using it as a model allows the machine to learn more accurately and generate music more smoothly. What I did was not to use MelodyRNN's pre-trained model for direct generation. Instead, I chose to train the model myself.


#### magenta github page:
    https://github.com/magenta/magenta


#### magenta MelodyRNN github and colab page:
    https://github.com/magenta/magenta/tree/main/magenta/models/melody_rnn
    https://colab.research.google.com/notebooks/magenta/hello_magenta/hello_magenta.ipynb#scrollTo=71dgCmmBli-s
    
    
From this note sequence:
 
![bokeh_plot](https://user-images.githubusercontent.com/73170220/174497519-eba32751-1154-4775-97b8-609dfd9bffc8.png)




https://user-images.githubusercontent.com/73170220/174500624-697a170b-1852-472e-8c09-99b00f63413b.mp4


  

To this (start with #C:
 
 
![bokeh_plot (1)](https://user-images.githubusercontent.com/73170220/174497579-5298298a-c7ff-49cf-a100-dc5412dc18b6.png)
 
 

https://user-images.githubusercontent.com/73170220/174500722-db4760f0-cb74-4060-baaf-0c3493a7f762.mp4


 
 
And this (using the up midi file as a start melody:
 
 
![bokeh_plot (2)](https://user-images.githubusercontent.com/73170220/174497716-08126cb0-d4dc-4e04-bc7d-267d8cbd14d9.png)


    
    
### I found that the generated sounds all have strong randomness. The music generated with the pre-music clips had more of the style and melody of the pre-music clips. This led me to think that if the pre-music snippets were also put through a machine learning process, would the resulting sounds be more varied?


### So I found another LSTM based model called MAGNet LSTM model to re-generated the sound clips and make it as guide of my generated melody. 


#### MAGNet colab page:

    https://colab.research.google.com/drive/1cCq-NNv62ofKU8rpx8uI_YwinWAeYZ7U?usp=sharing


#### I didn't change too much of this code and only changed a few that make it looks like more accuracte

    loss_type : "mse" -> "msle"
    
    number_rnn_layers : 2 ->  3
    
    rnn_number_units : 64 ->  128
    
    opt : Adam -> Adamax
    
But it makes every epoch become slower and uncleared:(


#### So I only changed those two:

    rnn_number_units : 64 ->  128
    
    opt : Adam -> Adamax
    
    
#### The loss become smaller

    Epoch 300/300
    18/18 [==============================] - 8s 421ms/step - loss: 0.0659
    
    
    Epoch 300/300
    13/13 [==============================] - 10s 805ms/step - loss: 0.0364
    
    
From this:

![download](https://user-images.githubusercontent.com/73170220/174500072-9b1e990a-b4ea-4ce9-bdfd-ec744b29e7a5.png)


To this:

![bokeh_plot (3)](https://user-images.githubusercontent.com/73170220/174500076-a254f0a3-ccd4-47f8-b6c9-960183904059.png)

### Finally, I used pre-trained song clip as staring clip!

![bokeh_plot (4)](https://user-images.githubusercontent.com/73170220/174500151-010d6954-b8b4-46a7-a996-d8bd5b98cb66.png)



#### Also, using the midi files as based note and add different sound effect:





Gituar:

https://user-images.githubusercontent.com/73170220/174500247-df409b9e-3389-4f04-a667-08092cda4191.mp4



Music box:



https://user-images.githubusercontent.com/73170220/174500288-a221e2cb-0990-48a3-9e0b-ccaf6deb7dfb.mp4



Piano:



https://user-images.githubusercontent.com/73170220/174500295-340f42ed-08fd-46e9-9c41-ce6253d8e546.mp4






