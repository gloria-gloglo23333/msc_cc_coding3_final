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


 
 
And this (using the previous midi file as a start melody:
 
 
![bokeh_plot (6)](https://user-images.githubusercontent.com/73170220/174501878-d2578306-f81f-499e-ae05-2901cc5f6b09.png)





https://user-images.githubusercontent.com/73170220/174501919-f72d7b75-b6f7-41f6-a92e-b33151ba8646.mp4



    
    
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


![download (1)](https://user-images.githubusercontent.com/73170220/174500885-526897a5-1ee2-4d65-a4ae-42d1d445b244.png)




https://user-images.githubusercontent.com/73170220/174500938-0303100a-45a8-4bbb-a2fb-d355c92a5851.mp4




To this:

![bokeh_plot (7)](https://user-images.githubusercontent.com/73170220/174502320-e6c39e7f-e3be-4546-8897-76e4b6c875d4.png)



https://user-images.githubusercontent.com/73170220/174502039-47b5e1e8-d57b-48cf-89f1-d57b45b5377f.mp4

Really bad right? :(


### Finally, I used pre-trained song clip as staring clip!

![bokeh_plot (8)](https://user-images.githubusercontent.com/73170220/174502337-68a331d0-43e5-4bb3-ad34-fe4fecf06b99.png)





https://user-images.githubusercontent.com/73170220/174502395-298284d3-ec74-4852-9869-7ea20de84150.mp4




Become a little better :( but is also awful :(



#### Also, I try to make some clips by using the midi files as based note and add different sound effect:





Gituar:

https://user-images.githubusercontent.com/73170220/174500247-df409b9e-3389-4f04-a667-08092cda4191.mp4




Music box:



https://user-images.githubusercontent.com/73170220/174500288-a221e2cb-0990-48a3-9e0b-ccaf6deb7dfb.mp4



Piano:



https://user-images.githubusercontent.com/73170220/174500295-340f42ed-08fd-46e9-9c41-ce6253d8e546.mp4




And that's it! :)

