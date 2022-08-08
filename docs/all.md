![](RackMultipart20220808-1-t7ao1q_html_f2c8f69bbc21670c.jpg)

![Shape1](RackMultipart20220808-1-t7ao1q_html_f8aaa488af7ece8.gif)

# cashiers of tomorrow

#

Grocery Vision is a computer vision application that simplifies the grocery checkout process. What does &quot;simpler&quot; mean? By simpler, we mean that users don&#39;t have to scan labels or memorize PLU codes.

We believe that computer vision, or more specifically object detection in this process, can be a solution to this problem because it provides a real-time way to detect objects in a variety that humans can only achieve after a long training period. However, in natural products such as in the fruit and vegetable department, there are also different shapes and colors, all of which can be assigned to one class and one product. There is a standard that must be followed to sell them as one product, but there remain natural differences between each fruit. Nevertheless, we have chosen this application for our Grocery Vision project.

To clarify the &quot;we&quot; briefly, we are 5 students from KIT who have a great interest in Data Science and software applications. That&#39;s why we all signed up for the AISS Applied in Computer Vision course and had a lot of fun together. We introduce ourselves a bit more detailed here.

In our application, we wanted to simplify the checkout process for products that need to be weighed. Our solution starts at the checkout. As you can see in the image, we use a camera that films a live video of the checkout.

![](RackMultipart20220808-1-t7ao1q_html_23a5dac341d96fa4.gif)

Using the neural network previously trained on synthetic data, our application automatically detects the items and lists them on the screen. The prices from the system are then assigned to the products and processed into the total after the purchase is complete.

Summary of benefits: easier shopping for supermarket customers, shorter training period for new store employees. And POS system providers can offer a centralized solution for weighing and automatic product detection.

# Content

[1.](#_Toc110879720)Business Case 5

[1.1.Motivation 5](#_Toc110879721)

[1.2.Setup 5](#_Toc110879722)

[1.3.Customer Relationship 6](#_Toc110879723)

[1.4.Subscription options 8](#_Toc110879724)

[1.5.Competitor Analysis 9](#_Toc110879725)

[1.6.SWOT-Analysis 10](#_Toc110879726)

[2.](#_Toc110879727)Business Strategy 11

[2.1.Industry Expertise 11](#_Toc110879728)

[2.2.Learnings 13](#_Toc110879729)

[2.3.Benefits 13](#_Toc110879730)

[2.4.Future Business strategy 14](#_Toc110879731)

[3.](#_Toc110879732)Data Generation 16

[3.1.Data Creation 16](#_Toc110879733)

[3.2.Labelling 17](#_Toc110879734)

[3.3.Our final dataset 17](#_Toc110879735)

[3.4.Possible Extensions 18](#_Toc110879736)

[3.5.Learnings 18](#_Toc110879737)

[4.](#_Toc110879738)Model 21

[4.1.Requirements 21](#_Toc110879739)

[4.2.Model 21](#_Toc110879740)

[4.3.Training 21](#_Toc110879741)

[5.](#_Toc110879742)Technical Implementation 24

[5.1.Overview 24](#_Toc110879743)

[5.2.Inference time optimization 25](#_Toc110879744)

[5.3.Backend 26](#_Toc110879745)

[5.4.Frontend 28](#_Toc110879746)

[5.5.Issues and Learnings 30](#_Toc110879747)

1.
# Business Case

  1.
## Motivation

Two familiar situations that probably everyone has experienced. First, you are at the supermarket and the cashier is scanning your products and everything is fine until the fruits and vegetables are about to be scanned. Suddenly, the cashier doesn&#39;t remember the PLU-codes and must either ask colleagues for assistance or look up the codes on one of the countless pages with all PLU-codes.

Or a different situation: You are waiting in line at the checkout and the person in front has forgotten that the store you are in doesn&#39;t weigh the fresh produce at checkout. So, the customer must rush back to the scale to weigh the goods. The result of both these situations is long waiting times, which nobody likes.

To solve these problems, our group has developed an innovative idea called Grocery Vision. The idea behind Grocery Vision is to implement Artificial Intelligence at supermarket checkouts. Specifically, it involves the use of computer vision to detect fruits and vegetables, making the checkout process much easier for the cashier. Grocery Vision will be setup as follows…

## 1.2. Setup

Figure 1 displays the how Grocery Vision will be implemented in supermarkets. The camera is installed directly above the scale, so it can detect the fruits and vegetables that the cashier is weighing at that moment. After placing the fresh produce on the scale our model will detect which fruit or vegetable is currently being weighed. Once the model detects the correct item, it receives the input of the weight from the scale via the cashier software. Our model then automatically calculates the price which then appears on the cashier display. Since the hardware installed in a supermarket checkout has limited computing power, our model will run on a Jetson Nano, which will be part of the Grocery Vision solution.

![](RackMultipart20220808-1-t7ao1q_html_23a5dac341d96fa4.gif)

_Figure 1: Setup of Grocery Vision in Supermarkets_

## 1.3. Customer Relationship

To determine Grocery Vision&#39;s customers and structure our business case, we used the Business Model Canvas framework. An overview of this framework can be seen in figure 2. Defining who our potential customers are, was the first question we needed to answer. At first it may seem obvious that the **supermarket retailers** are our main customers, as we plan to implement our Grocery Vision in supermarkets. However, as we are providing a product that needs to operate seamlessly with the already built-in hardware, the checkout counter, we also need to work together with the companies that build these checkout systems, which in our case are the **POS-System providers** (_POS = &quot;Point-of-Sale&quot;)._ Therefore, on the one hand we have the supermarket retailers as our direct customers and on the other hand the POS-System as strategic partners.

![Shape2](RackMultipart20220808-1-t7ao1q_html_e4de3021a3d9d7e7.gif)

_Figure 2: Business Model Canvas_

The Grocery Vision solution will be distributed in form of a **service bundle**. This means once a supermarket purchases Grocery Vision it will receive hardware, the camera and Jetson Nano, as well as access to the digital platform. The digital platform allows supermarkets to receive updates over the Internet. For example, if the fruit and vegetable assortment changes or new products are offered in the supermarket, the stores will always have the newest version of our model. Instead of selling Grocery Vision through the usual distribution channels, our goal is to create a **business ecosystem** that co-creates value for all involved parties. Figure 3 displays the fundamental actors within this ecosystem. Access to the business ecosystem will be on a s ![](RackMultipart20220808-1-t7ao1q_html_c5334deef2fdb42f.gif)
 ubscription basis. This means the supermarket will pay a fixed monthly fee which includes the usage of our hardware and grants them access to the digital platform. Supermarkets can

not only download the latest versions of our model from the platform, but also choose which subscriptions they want to purchase.

![](RackMultipart20220808-1-t7ao1q_html_da18a880c414221.gif)

_Figure 3: Business Ecosystem_

## 1.4. Subscription options

_Figure 4: Subscription Options_

A ![](RackMultipart20220808-1-t7ao1q_html_a8b991b3bedd6745.gif)
 s the profit margins and product ranges of individual supermarkets vary, stores will be able to choose between different subscriptions. Figure 4 provides an overview of the subscription options available to supermarkets.

The most simplistic version of our model will be the &quot; **basic**&quot; subscription. By choosing this option, the supermarket will receive both the hardware and access to the digital platform. While the model will still detect all the fruits and vegetables, the &quot;basic&quot; subscription will not be integrated into the cashier software. This means that it will only serve an informative purpose. It simply detects the items and informs the cashier which fruit or vegetable is being processed, saving the trouble of looking up the PLU codes. As this subscription option does not require scale integration it is very simple to install.

The &quot; **premium**&quot; subscription in contrast will require integration into the cashier software as it requires the input from the scale. This subscription option will also include the provision of hardware as well as access to the digital platform, however it will not only serve an informative purpose. Instead, it will combine the input from the scale with the object the camera detected to calculate the price. As this option is integrated into the cashier software the cashier does not need to take any further action.

The &quot; **ultimate**&quot; subscription option entails a complete system integration. This means our solution will no longer be required to provide the hardware, because the POS-System Provider will build checkout systems with an integrated camera. Obviously, this option will not be eligible in the early stages of our development. However, once our solution has demonstrated its applicability, POS-System Providers could be incentivized to build systems with an integrated camera and enough computing power to run our models.

## 1.5. Competitor Analysis

Today there are already few existing solutions that try to make shopping for groceries easier for customers and cashiers. In the following three cashierless alternatives are presented.

First, there are **Amazon Fresh/Go** supermarkets that don&#39;t require any cashiers because there is no checkout process necessary. Instead, these stores are equipped with cameras that track every move a customer makes. The customer must create an account and log in at the entrance. Then he can just pick up the items from the shelf he wants to buy and walk out of the store. Although this concept seems very promising for the future it does have a big down-side. According to Forbes, it takes an average of about a million dollars in hardware costs alone to open one of these stores. While these stores could become reality in some major cities, it is impossible for most supermarkets in Germany to invest such a large sum. In addition, the need to create an Amazon account and the fact that every movement is tracked with facial recognition may deter some potential customers.

Another alternative are **self-checkout** systems. More and more supermarkets are implementing these checkout systems as they do not require a cashier. While this proves beneficial from the supermarket operator&#39;s point of view, as it saves costs, it creates an additional effort for the customer. Moreover, it is often not possible to pay by cash which further lowers the acceptance of these checkouts. Furthermore, these systems are quite error-prone and often still require the attention of supermarket employees, thus eliminating their original benefit.

Lastly, **RFID-tags** are another cashierless alternative. This solution requires all items in the store to be equipped with RFID-tags. When the customer is then ready to checkout, all items are placed in the checkout bin and the POS system recognizes the labels and calculates the price. While this is an attractive solution for retailers selling clothing or sportswear, it is less optimal for supermarkets, as every fruit or vegetable would need a RFID-tag. This would not only cause additional costs but also waste resources.

## 1.6. SWOT-Analysis

**Strengths**

  - Faster checkout and reduced waiting times for customers
  - Reduced customer effort, as fresh produce is weighed at checkout
  - Faster training of supermarket employees and reduced personnel costs
  - Business ecosystem enables value co-creation for all involved parties

**Weaknesses**

- Model prototype can currently only detect a small number of items → Creating a functioning model that detects all items could be difficult
- Innovations need to be fully matured in order to be implemented in this industry

**Opportunities**

  - Partnerships with POS-System providers could help create a more sophisticated solution by integrating the camera into checkout system

**Threats**

  - Cashiers could see their jobs existentially threatened → Protests through workers&#39; unions
  - Large supermarket chains have their own software development departments that greatly exceed our resources

1.
# Business Strategy

## 2.1. Industry Expertise

Since our group had no prior experience in the supermarket industry, we decided to reach out to different industry experts. Not only did we contact many supermarket and discounter chains, but also a variety of POS-System providers. To our advantage, we received a reply from Manfred Kiffe, the managing director of PROCOM iPOS Systems GmbH, who told us that he would be happy to share his 30 years of know-how with us. In preparation for this telephone interview, we decided to formulate some questions we would like to get answered:

1. **Presentation of our idea/solution**

In general, Mr. Kiffe found our idea very good, and he mentioned a few times that we should not be discouraged. Beforehand we sent him a demo video so that he could get a better understanding of how our solution works. His opinion was that we came up with an innovative idea that could have a lot of potential. He also said that he had contacts to innovative partners that he could put us in touch with and that we could also contact the development department of his company that programs the POS software. Furthermore, he also told us to keep him informed about the development of our project and to contact him again if we have any questions.

1. **Overall potential of our solution**

Mr. Kiffe believed our solution could be successful in the medium to long term. For large chains (Edeka, Rewe) our solution would be attractive if we have a low error rate in our model. He said that in the supermarket industry the margins are very low and really attention is paid to every possible saving. Therefore, our solution would be relevant for the big chains if we could actually present a cost benefit, such as staff savings in the long run. Possible difficulties for us that he had mentioned were, among others, that the big chains like Edeka already have their own internal software houses that research innovative ideas long in advance of the actual implementation. He said that POS-Systems have an average life span of about 7 years and the contracts with the POS-System manufacturers are made well in advance. As a second hurdle, he said that in his eyes &quot;banal&quot; innovations take a very long time to appear on the market and are then also partly taken off the market again due to too high error rates. As an example, he had mentioned the voice output at the cash register, which e.g., says out loud the amount of change for the hearing impaired. Or also that many stores have partially implemented the self-service checkout, but since with this too often still employees had to intervene, were dismantled again. For these reasons, he felt that it might take a very long time for our solution to appear on the market.

1. **Is our idea with the interface to the POS-Software and the scale at all feasible?**

Regarding the interface Mr. Kiffe shared a lot of valuable information. First, he told us that it is quite difficult to create an interface directly to the scale. In order to use the scale directly, we would need a certification in Germany, which is issued by the Federal Physical-Technical Office in Braunschweig. This process is very complex and not even all POS-System manufacturers have such a certification. He also informed us that there is a whole guide which describes what is allowed and what is not (Welmec-Guide). Additionally, in stores that have such a certification, every 2 years the calibration office comes by and looks whether the scale still measures accurately. As this process is quite complex some supermarkets, especially the smaller ones, have no integrated scales in the cash registers. This is then also the reason why in some supermarkets customers must weigh the fresh goods themselves, as these stores do not have checkout systems with integrated scales. Therefore, he said that it is theoretically possible for us to create such an interface directly to the scale, but it could be associated with a lot of work. Instead, he presented a clever alternative. He said we could bypass this certification process if we do not create the interface directly to the scale, but to the POS software, which already has the certification in the ideal case.

1. **Would an integration of our solution into existing POS-Systems be at all possible?**

For the integration, Mr. Kiffe was of the opinion that it would make more sense in the first step to decouple the camera software and POS-System software, since this would avoid complications with the different operating systems. As a second step, or long-term solution, he said a direct integration into the POS system would be the optimal solution. However, this would require the POS-System provider to manufacture a system with an integrated camera.

1. **Do the POS-Systems have a GPU that would be capable of running a machine learning model?**

Mr. Kiffe said that the absolute top model has an i5 processor. However, this is not the standard. He informed us that most POS-Systems have an Intel J1900 or i3 processor. Therefore, GPU performance is very low. He also said that processes that are taken for granted by customers, such as contactless payments, sometimes push the POS system to the limit, since the WIFI connection in the stores is often not outstanding. On a side note, he also mentioned that a scanner scale costs about 2000€ and the associated cash POS-System another 2000€. This means that if a supermarket has several cash registers, this is a very large investment, especially for the smaller stores.

## 2.2. Learnings

With the help of our expert interview, we were able to gain many insights. The interview enlightened us that some of our original ideas were good in theory, but not feasible in practice. Initially, we planned to run our model either via a cloud-based platform or via the hardware of the POS system. However, we were told otherwise: firstly, the Internet connection would not be strong enough to run a cloud-based platform, and secondly, the built-in hardware would not be able to run our model.

## 2.3. Benefits

We want to conclude the business case with the gains that our application brings to the different business ecosystem participants. Our service has several benefits that can be attributed to the different players in the business platform we have created.

Let&#39;s first take a look at the supermarkets. Since they are the main customers or users of our supermarkets, they are the focus. In supermarkets, it is much easier to train new employees and the time required to do so can be shortened. This means that employees are ready to work faster, make fewer mistakes, especially in the initial phase, and therefore have higher productivity. And consequently, this leads to a reduction in personnel costs.

Another actor we have already introduced is the supermarket visitor or customer. The actual supermarket visitor or customer can go through the checkout faster and does not have to scan or weigh their products themselves. Compared to other checkout systems, this is a significant advantage and the customer experiences a much faster checkout. simply a simpler customer journey.

And finally with the last of the 3 players in our business ecosystem, the POS system provider. The POS system provider that would benefit from an integration of our service to have a clear advantage over their competitors with a sophisticated POS system. The main advantage is that the purchase of products can be handled without labeling or PLU codes. And the additional point is that it can easily adapt to changes in the product range.

## 2.4. Future Business strategy

Regarding the further development and implementation of Grocery Vision, we would have to decide on the future direction. In the meeting with the industry expert, Mr. Kiffe informed us that there are two potential future paths we could take. Figure 5 illustrates this crossroad.

![](RackMultipart20220808-1-t7ao1q_html_e1fde3499142218.png)

_Figure 5: Future Business Strategy_

The first path would be to try and make Grocery Vision a lucrative investment for one of the big supermarket chains. This means that we would be integrated into their own software development department. Therefore, instead of competing against a giant competitor we could collaboratively innovate our solution with the resources of a big company.

However, as this path could be difficult to reach, we could also try the second path. The second path would be to further develop Grocery Vision on our own. And instead of focusing on the big supermarket chains as potential customers, we would try to sell our solution to smaller independent stores. The advantage of this path would be that we would remain independent, i.e., we would continue to make our own strategic decisions in the future.

1.
# Data Generation

To gather sufficient data for training, we decided to create the data synthetically. Synthetic generation of training data allows us to create a large amount of data in a short time and allows for fast adaptability to new vegetables and fruits. Also, annotations can be stored at the same time as the picture is created. It is not necessary to manually label the pictures.

  1.
## Data Creation

For the realization of our proof-of-concept we decided to use a limited number of vegetables and fruits. The concept of creating synthetic data relies on using a random picture and printing the items that the model must detect on them.

In our case, one of 60 random background images served as the basis for the synthetic images. Since more than thousand images must be created for our training, 60 background images did not provide enough variety. Our initial tries revealed that adding additional noise to the background of the image improved the model&#39;s accuracy. Therefore, we added another step that modifies the background before placing the fruit and vegetable items on the background. We made use of a collection of random objects such as cars, screwdrivers, chairs, etc. which were randomly placed on the background. We also made sure to add hands to our collection of noise items. Adding a high number of noise items to the background ensures that the background of each image is unique.

We limited the model to detect only a handful of fruits and vegetables:

| Eggplant | Avocado | Cucumber | Sweet Potato | Lemon |
| --- | --- | --- | --- | --- |
| ![](RackMultipart20220808-1-t7ao1q_html_57915a2aa548db6f.png) | ![](RackMultipart20220808-1-t7ao1q_html_2e60c398f158fba6.png) | ![](RackMultipart20220808-1-t7ao1q_html_f5b72d0744e0cb28.jpg) | ![Grafik 11](RackMultipart20220808-1-t7ao1q_html_669600f36d7af8e0.gif) | ![](RackMultipart20220808-1-t7ao1q_html_fd93d74943ab54c.png) |

We took 30 to 40 pictures for each vegetable and fruit class. Most of the pictures were taken by us. In a second step, we used an image editing program to cut out the individual objects to get rid of the background. Some images were used from the &quot;Fruits360&quot; Dataset from Kaggle.com. The cut-out elements were then randomly placed on the background images after applying modifying the background with noise items. To improve the class predictions of our model, we randomly rotate and resize each object before placing it on to the picture. We also allow overlapping of up to 10%. Overlapping ensures that the model detects the vegetables early, even if there are still hands covering the vegetables or fruits or the vegetables and fruits cover each other to a certain degree. Our final images that we used to train our model had about 1-5 vegetable and fruit objects.

The images we used to create our synthetic data can be accessed [here:](https://drive.google.com/drive/folders/1I6pUovgsugu6mKjATuBTfGWS__Y3UDxg?usp=sharing)

[https://drive.google.com/drive/folders/1I6pUovgsugu6mKjATuBTfGWS\_\_Y3UDxg](https://drive.google.com/drive/folders/1I6pUovgsugu6mKjATuBTfGWS__Y3UDxg)

  1.
## Labelling

The location of an item plotted on the image is randomly chosen and stored to a text file at the same time. Since we are training a Yolo model, the format in which class and location information is stored to the corresponding conventions.

  1.
## Our final dataset

By creating synthetic images, we can assume that we have avoided making man-made errors like grouping, positioning or selection are bypassed. However, we cannot exclude that our generated images are not completely unbiased. The way we captured images and cropped the objects is a key element for creating our data. Errors on this level can have a strong impact on the synthetically generated images.

Our final dataset consisted of 7000 images which we split into 80% training data and 20% test data.

![](RackMultipart20220808-1-t7ao1q_html_f2a8a0d848f7a35d.jpg)
 ![](RackMultipart20220808-1-t7ao1q_html_848a8e4a6c1bf8a.png)
 ![](RackMultipart20220808-1-t7ao1q_html_7382fe79056707eb.jpg)

_Figure 6: Relative x and y position of the fruit and vegetables items on the images_

_Figure 8: Number of instances per class summarized over all generated images_

_Figure 7: Relative height and width size of the items_

  1.
## Possible Extensions

1. **Introducing new objects**

Introducing new elements is a challenge for our model. To add new objects to the model we would use transfer learning. This is done by transferring the learning progress of the existing model to the new one. This results in advantages such as faster creation, better model quality and less resource usage.

1. **Improving the model**

Furthermore, our model can be improved by active learning. In active learning mode, every object detection that is not recalled by the cashier is perceived as correct. Any object detection that is recalled by the cashier is perceived as false. This mode requires special attention from the cashiers. However, if our system is used in large supermarket chains, the effort would be very limited, due to having only a few cashiers work in active learning mode for only a few hours creates large amount of data. The amount of additional training data that would be generated would quickly improve the models with little effort.

  1.
## Learnings

1. **Background Noise**

We started generating our data by just using the 60 backgrounds randomly and adding the items that had to be detected by the model. Creating large amounts of data without adding further noise to the background does not provide enough variety to the picture for the model to learn the item classes well. Adding additional noise items helps to create a unique background each time and improves the model&#39;s performance.

1. **Cut Out**

Cropping out images is error prone. Most of us used the &quot;Preview&quot;-App from the Mac to cut out the objects from the original picture. The &quot;Preview&quot;-App offers different tools for that task. There are two main features that we used in the beginning:

- _Intelligent Lasso_

The intelligent Lasso helps the user to cut out objects, by only having to draw a rough outline around the object.

- _Magic wand_

The magic wand works color based. The user sets a start point on the picture and the software adds pixels to the mask based on the degree that the user defines. Magic wand works best if there is a strong contrast between the subject that has to be cut out and the background (e.g.: eggplant on a white background).

![Shape7](RackMultipart20220808-1-t7ao1q_html_5b485188f91ef39f.gif)

_Figure 10: Pixel defect leads to unnecessary large bounding boxes (see yellow box)_

_Figure 9: The yellow-colored area is the cut-out item after using the magic wand. Some pixels which do not belong to the sweet potato were also cut out (see far right)_

A ![](RackMultipart20220808-1-t7ao1q_html_bea580c4e8e0689a.png)
 ![](RackMultipart20220808-1-t7ao1q_html_8e2be485ad3bc353.png)
 lthough the magic wand is the easier tool to use, it caused problems. Oftentimes pixels far outside of the actual objects were also added to the mask.

Since it was mostly just a few pixels and not a larger area we did not see it at first and came across this issue at a very late stage of the project. The problem with this is that the bounding box is drawn too large, and the quality of the model is compromised. (See Figure 10)

1. **Image variety**

As for everything in machine learning, it is true that the model is only as good as the data that is used to train the model. We started with only a few images per class and quickly noticed that there was not enough variety in the original images of objects that we created for generating our data. E.g.: initially we had a red bell pepper in our data set. All the bell pepper pictures that we used for training had a white reflection somewhere on the skin. The model did perform well on the synthetic test data. When used in the development process, the model detected bell peppers more frequently even if no peppers were shown. Our guess is that the model was overfitted due to the white reflection that every original bell pepper image had.

1.
# Model

  1.
## Requirements

Our model imposes technical requirements:

- It must be able to detect multiple classes
- It must run in real time
- It must be small enough to run on the Jetson Nano

Our model imposes qualitative requirements:

To measure the quality of our model, we did not focus solely on metrics but rather on satisfying our use case:

_One or more fruit and/or vegetable items are brought into the scene. The objects are included in the POS system if the objects are detected by the model over a certain time period t._

As for specific values we set our goal to detect an item for t =1.5 seconds. If our model does not make any mistakes during the process of a simulated purchase process, we would consider our quality requirement as satisfied.

  1.
## Model

Out of the many object detection algorithms, we decided to use the YOLO framework after research. Yolo is based on a CNN structure and detects objects in real time. Because of the CNN structure, the algorithm requires only a single forward propagation in the neural network to detect objects. Furthermore, Yolo detects multiple classes and their bounding boxes simultaneously.

  1.
## Training

We trained our model with a [Google Colab Notebook](https://colab.research.google.com/github/roboflow-ai/yolov5-custom-training-tutorial/blob/main/yolov5-custom-training.ipynb#scrollTo=eaFNnxLJbq4J). The resources Google provides were enough for our project. Of the different model sizes, we opted for the smallest &quot;Yolo5n&quot;. We trained our model with a batch size of 16 and an epoch size of 50.

[https://colab.research.google.com/github/roboflow-ai/yolov5-custom-training-tutorial/blob/main/yolov5-custom-training.ipynb#scrollTo=eaFNnxLJbq4J](https://colab.research.google.com/github/roboflow-ai/yolov5-custom-training-tutorial/blob/main/yolov5-custom-training.ipynb#scrollTo=eaFNnxLJbq4J)

![](RackMultipart20220808-1-t7ao1q_html_78541e9e4c7d30e8.png)
 ![](RackMultipart20220808-1-t7ao1q_html_4765e41217870424.png)

_Figure 11: Confusion matrix of predicted and actual labels_

_Figure 12: Metrics matrix of our final model_

After 30 epochs of training (Figure 12), one can already observe a clear approximation of metrics. In the following training up to the last epoch the model is improved even more. After the 50 epochs training the model was tested on the test set with good results. The test set was designed in the same way as the entire dataset and was separated by a train\_test\_split before training. This means that the test ser also consists of purely synthetic generated data. From this, the confusion-matrix shown in Figure 11 was obtained. The number of incorrectly detected objects from other classes is very low on the test set and promises good performance.

1.
# Technical Implementation

  1.
## Overview

As mentioned in the former section, we used the YoloV5 architecture for our object detection task. We utilized the comprehensive repository from [ultralytics](https://github.com/ultralytics/yolov5), which already provided the necessary tools to get us started. As this repository used PyTorch, this was a key dependency for us. Furthermore, to get the video stream from the CSI-camera from the Jetson Nano we used a combination of Gstreamer and OpenCV, which allowed us to run our inference with Yolo framework on each recorded frame.

In order to present the respective results, the frame that was used for inference was augmented with the bounding boxes around the detected objects with the respective classes and scores.

As this detection was only one part of our solution, we passed the augmented frame to a webpage where our results were presented in a user-friendly frontend, which was built using HTML, JavaScript and CSS while taking also use of the frontend framework Bootstrap and the JavaScript library JQuery. The communication between the Python backend and the webpage was managed by a combination of Flask and SocketIO.

_Figure 13: Techstack_

F ![](RackMultipart20220808-1-t7ao1q_html_862c952dfab9cc8f.png)
 urthermore, we speed up our inference time using the ONNX runtime engine. An overview of our techstack is summarized in Figure 13.

  1.
## Inference time optimization

We first started out using vanilla PyTorch on the CPU for our inference, which turned out to be rather slow as the inference time for one image already took 0,5 seconds, so we could only run our video stream at 1 Frame per second (FPS). As we already used the nano version of the yolo architecture, so the smallest version of the CNN available, we had to find other ways to improve our inference speed. The final solution that we came across was the ONNX runtime engine, an open-source project which is specifically designed to accelerate the machine learning process, in particular the inference step.

We implemented the ONNX runtime engine by utilizing the [yoloRT](https://zhiqwang.com/yolov5-rt-stack/) repository, which made it particularly easy to transform an already existing model in the PyTorch format to the ONNX format. The main simplification provided by this repository is that the transformation of the model format also respects changes that are necessary to use the inference using the ONNX runtime engine in a way that further augmentation of the results is not necessary, like preprocessing the shape of the processed image for a correct display of the bounding boxes. Using this solution, we were able to decrease the inference time by about 44%, from 500ms to 280ms. This allowed us to run our model on 3 FPS, which worked quite well for our solution.

However, this solution still uses the CPU, as we had problems installing the required packages for our Python version with GPU support.

The Jetson nano already comes preinstalled with the most used machine learning libraries, compiled with GPU support, however only for the preinstalled Python version 3.6.9. The repositories that we used required us to use Python 3.8 or higher, so we could not use the preinstalled packages in our environment. When we reinstalled the respective packages from PyPi, all of them only supported the CPU or had to recompiled from source with GPU support enabled.

Regardless of these restrictions, with the help of group 2 we found a prebuilt Python wheel for the ONNX runtime engine with GPU support, which could be downloaded and easily installed into our environment. By utilizing the GPU, we could gain a massive improvement of again reducing our inference time by 78.5% down to 60ms, which allowed us to run our model 7FPS. A summary of the inference time improvements is shown in Figure 14: Inference time speed-up.

![](RackMultipart20220808-1-t7ao1q_html_2bffeadb20b0e2e8.png)

_Figure 14: Inference time speed-up_

  1.
## Backend

As mentioned above, we implemented a web application with the microframework Flask. We opted for Flask because, as a microframework, Flask has only a few dependencies, which makes it lightweight and secure. It is widely used (Netflix, Airbnb…) and the industry standard in Python when it comes to doing nearly anything with HTTP Protocol in Python.

In our &quot;app.py&quot; we create a flask app, a Flask-SocketIO server and run the SocketIO web server with the flask app instance as a parameter. By default, the server listens on the localhost (127.0.0.1.) with port number 5000.

We defined two endpoints &#39;/&#39; and &#39;/video&#39; to handle HTTP GET requests. The &#39;/&#39; endpoint renders the index.html file, which is the view the cashier sees. &#39;/video&#39; returns a [Response](https://flask.palletsprojects.com/en/2.2.x/api/#flask.Response) object whose response is the augmented frame of the OpenCV video stream. The server uses the &#39;multipart/x-mixed-replace&#39; HTTP header to push dynamically updated content to the web browser. It works by instructing the browser to keep the connection open and replace the displayed web page or piece of media with another when it receives a special token (defined with boundary). This is how the video is streamed to the browser.

_Figure 15: Endpoints_

 ![](RackMultipart20220808-1-t7ao1q_html_45cf311cddb0ece2.gif)

For each frame it is documented which product category (e.g. lemon) and how many objects (&quot;count&quot;) of this category were detected. It is also recorded for how many frames (&quot;since\_frames&quot;) a certain number of products of a category have been detected.

_Figure 16: Report dictionary_

 ![](RackMultipart20220808-1-t7ao1q_html_c6e57bafebfd90ff.gif)

A product needs to be detected for a certain number of consecutive frames in order to be added to the shopping cart. The duration in which an item must be detected to be added to the shopping list is determined by two components: First, the framerate and second, the &quot;number of frames&quot; threshold (we set it to 11 Frames). If the threshold is reached and a product is detected for 11 frames, a server generated SocketIO event &#39;detected\_objects&#39; is emitted to the connected client. This is how changes are communicated between backend and frontend.

  1.
## Frontend

_Figure 17: Grocery Vision Frontend_

W ![](RackMultipart20220808-1-t7ao1q_html_fce9778cd1a8a6e2.png) e added a user-friendly frontend to our Grocery Vision prototype in order to demonstrate the functionality in a real-life way.

Figure 17 shows the frontend the cashier sees at the POS checkout screen when using Grocery Vision. On the left side of the screen, the shopping list is displayed with all necessary information such as item name, picture, price, quantity and the calculated subtotal. On the right side of the screen, the video stream from the jetson nano&#39;s CSI camera is displayed. In the bottom right corner, the total sum of the current purchase is shown as well as there is a green button that allows the cashier to complete the purchase.

_Figure 18: Object(s) to be added to the shopping cart._

All the cashier has to do is to put the item in front of the camera. After a certain number of frames in which the item is detected, it is added to the shopping list on the left side of the screen. For getting updates the frontend subscribes to the SocketIO connection &#39;detected\_objects&#39;, which returns a dictionary of the following kind: ![](RackMultipart20220808-1-t7ao1q_html_c01094aa38e14dea.gif)

In this dictionary, the item (here: label = lemon) and its quantity (here: count=1) that needs to be added to the shopping cart is given. The updates of the shopping cart and its visualization is handled with JavaScript.

Figure 19 shows the process of a purchase, where picture (1) shows the starting screen. In (2) the first product (sweet potato) is put in front of the camera. After the sweet potato is detected during a certain number of frames, it is added to the shopping list (3). The cashier continues like this and moves on to the next products. After the last products are put in front of the camera (4) the cashier clicks on the green &quot;check order&quot; button to check out the order. In a final step the cashier can now do adjustments to the order before completing the purchase so that the order is processed (6).

_Figure 19: Grocery Vision supermarket checkout process._

 ![](RackMultipart20220808-1-t7ao1q_html_c2c81f8a5c913624.gif)

  1.
## Issues and Learnings

_Figure 20: Main compatibilityissues_

A ![](RackMultipart20220808-1-t7ao1q_html_f18def858ad3dab8.png)
 s in every project we came across multiple issues, however most of them can be summarized under &quot;Compatibility issues&quot;. A short overview is given in figure 20.

As mentioned in the inference section, we had trouble installing the necessary packages with GPU support, since due to our dependencies we were required to use Python 3.8 or newer, however the preinstalled packages with GPU-support that came with the Jetson Nano could only be used with Python 3.6.9. If the packages were installed via pip, the corresponding packages only had CPU support.

Moreover, at the beginning of our project we started developing a solution on our personal computers that accessed the webcam of a computer via JavaScript, however when we deployed the solution on the Nano, we realized that solution does not work, as the used CSI-Camera was not detected as a webcam. Since we did not find an appropriate solution to this problem, we had to start over with a new solution.

The main learning we took from this is that we want to increase our use of OS agnostic software solution like Docker, in order to prevent these mistakes from happening again.