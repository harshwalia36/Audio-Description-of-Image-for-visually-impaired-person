# Audio-Description-of-Image-for-visually-impaired-person

### Idea behind the project is to convert the image -> caption -> audio

I have implemented the image captioning with 2 approaches-

V1). Implemented ****CNN-RNN(LSTM)**** Architecture to convert the image into caption which acheived a `LOSS of 2.689` on Flickr 8K dataset.  <br>
V2). Implemented ****CNN-RNN Architecture with Attention Mechanism**** to acheive better accuracy .Used a Larger MSCOCO Dataset of 327437 sample images which acheived a `LOSS of 1.625`. 


## Simple CNN-RNN Architecute

![image](https://user-images.githubusercontent.com/43993467/115182969-8b0ab380-a0f8-11eb-89fd-af80c6143f8f.png)

<br>

## Now, How the 2nd approach using Attention Mechanism improved the model

<br>

![image](https://user-images.githubusercontent.com/43993467/115183070-bee5d900-a0f8-11eb-9e1d-d86012adbe85.png)


## MATHS Behind the Attention Mechanism

Local Attention
As Global attention focus on all source side words for all target words, it is computationally very expensive and is impractical when translating for long sentences. To overcome this deficiency local attention chooses to focus only on a small subset of the hidden states of the encoder per target word.

Every location of convolution layers corresponds to some location of image as shown below.

![image](https://user-images.githubusercontent.com/43993467/115183164-e5a40f80-a0f8-11eb-8c7c-2b93b47642fc.png)


#### Taking an example
Now, for example, the output of the 5th convolution layer of Inception is a 14 * 14 * 512 size feature map.
This 5th convolution layer has 14*14 pixel locations which corresponds to certain portion in image, that means we have 196 such pixel locations. And finally, we can treat these 196 locations(each having 512 dimensional representation) .

The model will then learn an attention over these locations(which in turn corresponds to actual locations in the images).

![image](https://user-images.githubusercontent.com/43993467/115183372-429fc580-a0f9-11eb-93e2-417125c4a453.png)

Let’s discuss equations for Local Attention and Global Attention with General score :

![image](https://user-images.githubusercontent.com/43993467/115183399-50554b00-a0f9-11eb-936f-8f05950ae10b.png)

![image](https://user-images.githubusercontent.com/43993467/115183421-58ad8600-a0f9-11eb-9193-f5a1675424d4.png)

## Some Models predictions on test dataset

##### These descriptions are converted to audio in CODE

![image](https://user-images.githubusercontent.com/43993467/115183753-16387900-a0fa-11eb-8f4e-f26b319812ee.png) 
<sos> pizza with pier and paper on it <eos>
 <br>
  
![image](https://user-images.githubusercontent.com/43993467/115183810-349e7480-a0fa-11eb-87a6-f180a83ee562.png) 
<sos> plane bear with sized zebras on it <eos>
 <br>
  
![image](https://user-images.githubusercontent.com/43993467/115183902-5697f700-a0fa-11eb-8854-bdb57431caf9.png) 
<sos> zebra standing next to car in batter <eos>
 <br>
  
  
 ![image](https://user-images.githubusercontent.com/43993467/115184014-94951b00-a0fa-11eb-9cb1-b79f6bf208ef.png) 
 <sos> woman in lamb group is holding skis <eos>
 <br>
  
 ![image](https://user-images.githubusercontent.com/43993467/115184071-ae366280-a0fa-11eb-88d8-fd4198adecbe.png)
 <sos> display case filled with lots of different kinds of donuts <eos>

<br>

![image](https://user-images.githubusercontent.com/43993467/115184196-eccc1d00-a0fa-11eb-84f7-168a4abe1501.png)
<sos> wall mens truck is parked in grass <eos>
 
 <br>
 
![image](https://user-images.githubusercontent.com/43993467/116770206-5afbd280-aa5f-11eb-861b-2683ac275972.png)
<sos> black and white cat standing in his of patch phones <eos>





