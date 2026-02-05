# Waste Detection and Classification
## Researcher - Fatima Aghapourasl

Purpose - This repository was completed as a graded project in partial fulfillment of the requirements for the postgraduate studies
Background

The increasing volume of waste production in urban environments poses significant challenges for municipal waste management systems. With landfills nearing capacity and recycling rates lagging behind production, there is a critical need for innovative solutions to promote efficient waste sorting and recycling. While specific statistics may vary depending on the region and context, globally, urban areas generate substantial waste, with projections indicating a steady increase in waste production over the coming years. For instance, according to the World Bank, urban waste generation is expected to rise from 2.01 billion tonnes in 2016 to 3.40 billion tonnes by 2050 (World Health Organization, 2024). Toronto's economy produces around 2.1 million tons of solid waste annually, with projections increasing to 2.5 million tons by 2030 if current trends persist (Circle Economy, 2022).

The motivation behind WasteWise Toronto is to leverage advanced machine learning and data science techniques to improve sorting accuracy, thus enhancing recycling efforts and reducing the overall environmental footprint of urban waste management.

About the Dataset
A mixed Waste dataset was used for this project. It comprised 6,884 images images 416x416 colour images in 11 classes. The training images were 4800, testing images were ¬1000 and validation images were ¬1000 in quantity. The classes in the dataset included: 'cans', 'tins', 'metal_trays_plates_pans','cardboard', 'styrofoam container', 'envelope', 'paper', 'carton', 'plastic', 'organics', 'general'
¬2100 were recyclables, ¬2100 organics, ¬2100 general
The following pre-processing steps was applied to each image:

Auto-orientation of pixel data (with EXIF[Exchangeable Image File Format]-orientation stripping)
Resize to 416x416 (Stretch) N.B - EXIF-orientation stripping involves analyzing the orientation information stored in the EXIF metadata and rotating or flipping the image data accordingly to ensure that it is displayed correctly.
The following augmentation was applied to create 3 versions of each source image:

50% probability of horizontal flip
50% probability of vertical flip
Equal probability of one of the following 90-degree rotations: none, clockwise, counter-clockwise, upside-down
Random shear of between -15° to +15° horizontally and -15° to +15° vertically
Reference Provided by a Roboflow user License: CC BY 4.0
Blue Bin:Recyclables

Metals ('cans', 'tins', 'metal_trays_plates_pans'): https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2?select=metal
Cardboard boxes: https://universe.roboflow.com/dataset-t7hz7/cardboard-eupc8/dataset/3
Styrofoam containers : https://universe.roboflow.com/namseoul-qobk6/styrofoam-qt1kt/dataset/1 Envelopes: https://universe.roboflow.com/mateo-ojeda/envelope-c6750/dataset/1 - Paper: https://universe.roboflow.com/natalie-perrochon-yqnhb/recycling-try-2/dataset/16
Carton juice and milk boxes: https://app.roboflow.com/waste-z6zen/carton-xuife/1
Plastic bottles: https://universe.roboflow.com/betul-rt4lp/plastic-bottle-cuwtu/dataset/1
Green Bin: Organics (fruits, vegetables, scraps from plates and garbage dumps, rotting foods) https://universe.roboflow.com/patata-man-y8maj/bio-waste/browse?queryText=&pageSize=50&startingIndex=0&browseQuery=true https://universe.roboflow.com/search?q=organic%20waste

Black Bin: General waste

mugs: https://universe.roboflow.com/gsa-team/mugs-vhjth
broken plates: https://app.roboflow.com/waste-z6zen/general-1/1
cigarettes: https://universe.roboflow.com/universitadellacalabria-icrla/cigarettebuttdetection-tlhei
Masks and gloves: https://universe.roboflow.com/sultana-almasoud/our_gp2
About the Model
For the Object Detection Model, YOLOv8n was selected over YOLOv5 due to its potential for balancing speed and accuracy, supported by ample help, documentation, and community resources.

Findings
The Yolov8n model was trained via supervised learning, with predictions based on class labels and bounding boxes indicating waste coordinates within the image dataset. Through experimentation with hyper-tuning parameters, the most optimal values (50 epochs, 64 batch size, 0.0001 learning rate, 0.15 dropout) were identified, resulting in a notable decrease in loss scores and an increase in precision values, indicative of improved detection accuracy. Despite training the model on a relatively small dataset of 4800 images and 50 epochs, the waste detection model achieved an overall precision of 72.6%, with 7 out of the 11 classes demonstrating very good precision scores ranging from 73% to 98%.

References
Circle Economy, 2022. Lessons from North America: How Toronto is going Circular. https://www.circle-economy.com/blogs/lessons-from-north-america-how-toronto-is-going-circular
World Health Organization, 2024. What a Waste 2.0. https://datatopics.worldbank.org/what-a-waste/#:~:text=As%20nations%20and%20cities%20urbanize,through%20open%20dumping%20or%20burning.
About
This repository supports waste detection and classification using the pretrained YOLOv8n Model, which was further trained and finetuned using waste image data from Roboflow.


# WasteWise Application
This directory contains the WasteWise Toronto Application, the Business Pitch with Technical presentation and the report.

Description
WasteWise is a smart waste management app for the City of Toronto. Its AI-powered features include an object detection model for images that detects and predicts object classes. From that, the app generates the correct disposal bin (blue for recycling, green for compost/organics, black for garbage) for the waste object, as well as a chatbot to answer waste management-related questions.

For Quick Testing of the Demo Application in a Web Browser
Go to https://cors-anywhere.herokuapp.com and request temporary access to the demo server
Go to URL: https://marvelous-fudge-4b7368.netlify.app
Test the WasteWise Toronto app (see guide below)

# Application Screens (Android)
### Splash Screen

<img width="200"  alt="Splash" src="https://github.com/user-attachments/assets/d04ad5c0-4e8d-4280-9b88-db9de123ca41" />

### Intro Pages (component 'Intro' attached to home page)

 <img width="200"  alt="Intro2" src="https://github.com/user-attachments/assets/44827acc-1c02-4e75-8807-0db78ae0bd06" />
<img width="200"  alt="Intro1" src="https://github.com/user-attachments/assets/9c03341e-199b-4642-8ce6-139e0388d10c" />


### Home Page (Collection Schedule and Drop-off Depots features are disabled)

<img width="200"  alt="Home" src="https://github.com/user-attachments/assets/3e6da969-0de0-4d8e-ac6e-1fde769f204e" />


### Recycle, Compost, Garbage, Yard pages (all sharing the same page format 'WasteSetOutTips.tsx')

<img width="200"  alt="Compost" src="https://github.com/user-attachments/assets/646d797c-03b9-413e-930a-ed6a508684ac" />
<img width="200" " alt="Garbage" src="https://github.com/user-attachments/assets/8a29afd4-d3ab-430f-b5ce-1d9d671ad0dd" />
<img width="200"  alt="Recycle" src="https://github.com/user-attachments/assets/fa8b4345-cce2-4c3c-b592-120bdec0c35c" />
<img width="200"  alt="Yard" src="https://github.com/user-attachments/assets/e064dece-e139-41c0-a4cd-d3ac0001a5c6" />

### Scan and Sort Page

<img width="200"  alt="Scan SortResult" src="https://github.com/user-attachments/assets/6f93cc39-6c5d-44c7-89b1-f41037a067c7" />
<img width="200" alt="Scan Sort" src="https://github.com/user-attachments/assets/2dc0dea0-4fbc-4363-b4b0-1b83442aee5f" />


### Chatbot page

 
<img width="200"  alt="Chatbot" src="https://github.com/user-attachments/assets/c5243983-a338-4466-b8d8-ee9c3ce0f12f" />
<img width="200"  alt="Chatbot_Intro" src="https://github.com/user-attachments/assets/58cea0ba-83a5-4827-aacf-34ba0dfb622b" />

