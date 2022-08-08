# Business Case

## Motivation

Two familiar situations that probably everyone has experienced. First, you are at the supermarket and the cashier is scanning your products and everything is fine until the fruits and vegetables are about to be scanned. Suddenly, the cashier doesn&#39;t remember the PLU-codes and must either ask colleagues for assistance or look up the codes on one of the countless pages with all PLU-codes.

Or a different situation: You are waiting in line at the checkout and the person in front has forgotten that the store you are in doesn&#39;t weigh the fresh produce at checkout. So, the customer must rush back to the scale to weigh the goods. The result of both these situations is long waiting times, which nobody likes.

To solve these problems, our group has developed an innovative idea called Grocery Vision. The idea behind Grocery Vision is to implement Artificial Intelligence at supermarket checkouts. Specifically, it involves the use of computer vision to detect fruits and vegetables, making the checkout process much easier for the cashier. Grocery Vision will be setup as follows…

## Setup

Figure 1 displays the how Grocery Vision will be implemented in supermarkets. The camera is installed directly above the scale, so it can detect the fruits and vegetables that the cashier is weighing at that moment. After placing the fresh produce on the scale our model will detect which fruit or vegetable is currently being weighed. Once the model detects the correct item, it receives the input of the weight from the scale via the cashier software. Our model then automatically calculates the price which then appears on the cashier display. Since the hardware installed in a supermarket checkout has limited computing power, our model will run on a Jetson Nano, which will be part of the Grocery Vision solution.

![Setup Application](assets/images/Setup%20of%20Grocery%20Vision%20in%20Supermarkets.png)

_Figure 1: Setup of Grocery Vision in Supermarkets_

## Customer Relationship

To determine Grocery Vision&#39;s customers and structure our business case, we used the Business Model Canvas framework. An overview of this framework can be seen in figure 2. Defining who our potential customers are, was the first question we needed to answer. At first it may seem obvious that the **supermarket retailers** are our main customers, as we plan to implement our Grocery Vision in supermarkets. However, as we are providing a product that needs to operate seamlessly with the already built-in hardware, the checkout counter, we also need to work together with the companies that build these checkout systems, which in our case are the **POS-System providers** (_POS = &quot;Point-of-Sale&quot;)._ Therefore, on the one hand we have the supermarket retailers as our direct customers and on the other hand the POS-System as strategic partners.

![Business Model Canvas](assets/images/Business%20Model%20Canvas.png)

_Figure 2: Business Model Canvas_

The Grocery Vision solution will be distributed in form of a **service bundle**. This means once a supermarket purchases Grocery Vision it will receive hardware, the camera and Jetson Nano, as well as access to the digital platform. The digital platform allows supermarkets to receive updates over the Internet. For example, if the fruit and vegetable assortment changes or new products are offered in the supermarket, the stores will always have the newest version of our model. Instead of selling Grocery Vision through the usual distribution channels, our goal is to create a **business ecosystem** that co-creates value for all involved parties. Figure 3 displays the fundamental actors within this ecosystem. Access to the business ecosystem will be on a subscription basis. This means the supermarket will pay a fixed monthly fee which includes the usage of our hardware and grants them access to the digital platform. Supermarkets can not only download the latest versions of our model from the platform, but also choose which subscriptions they want to purchase.

![Business Ecosystem](assets/images/Business%20Ecosystem%20of%20Grocery%20Vision.png)

_Figure 3: Business Ecosystem_

## Subscription options

As the profit margins and product ranges of individual supermarkets vary, stores will be able to choose between different subscriptions. Figure 4 provides an overview of the subscription options available to supermarkets.

The most simplistic version of our model will be the &quot; **basic**&quot; subscription. By choosing this option, the supermarket will receive both the hardware and access to the digital platform. While the model will still detect all the fruits and vegetables, the &quot;basic&quot; subscription will not be integrated into the cashier software. This means that it will only serve an informative purpose. It simply detects the items and informs the cashier which fruit or vegetable is being processed, saving the trouble of looking up the PLU codes. As this subscription option does not require scale integration it is very simple to install.

The &quot; **premium**&quot; subscription in contrast will require integration into the cashier software as it requires the input from the scale. This subscription option will also include the provision of hardware as well as access to the digital platform, however it will not only serve an informative purpose. Instead, it will combine the input from the scale with the object the camera detected to calculate the price. As this option is integrated into the cashier software the cashier does not need to take any further action.

The &quot; **ultimate**&quot; subscription option entails a complete system integration. This means our solution will no longer be required to provide the hardware, because the POS-System Provider will build checkout systems with an integrated camera. Obviously, this option will not be eligible in the early stages of our development. However, once our solution has demonstrated its applicability, POS-System Providers could be incentivized to build systems with an integrated camera and enough computing power to run our models.

![Subscription Options](assets/images/Subscription%20Options.png)

_Figure 4: Subscription Options_


## Competitor Analysis

Today there are already few existing solutions that try to make shopping for groceries easier for customers and cashiers. In the following three cashierless alternatives are presented.

First, there are **Amazon Fresh/Go** supermarkets that don&#39;t require any cashiers because there is no checkout process necessary. Instead, these stores are equipped with cameras that track every move a customer makes. The customer must create an account and log in at the entrance. Then he can just pick up the items from the shelf he wants to buy and walk out of the store. Although this concept seems very promising for the future it does have a big down-side. According to Forbes, it takes an average of about a million dollars in hardware costs alone to open one of these stores. While these stores could become reality in some major cities, it is impossible for most supermarkets in Germany to invest such a large sum. In addition, the need to create an Amazon account and the fact that every movement is tracked with facial recognition may deter some potential customers.

Another alternative are **self-checkout** systems. More and more supermarkets are implementing these checkout systems as they do not require a cashier. While this proves beneficial from the supermarket operator&#39;s point of view, as it saves costs, it creates an additional effort for the customer. Moreover, it is often not possible to pay by cash which further lowers the acceptance of these checkouts. Furthermore, these systems are quite error-prone and often still require the attention of supermarket employees, thus eliminating their original benefit.

Lastly, **RFID-tags** are another cashierless alternative. This solution requires all items in the store to be equipped with RFID-tags. When the customer is then ready to checkout, all items are placed in the checkout bin and the POS system recognizes the labels and calculates the price. While this is an attractive solution for retailers selling clothing or sportswear, it is less optimal for supermarkets, as every fruit or vegetable would need a RFID-tag. This would not only cause additional costs but also waste resources.

## SWOT-Analysis

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
