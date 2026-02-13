#  Custom Object Detection model with DEEPCRAFT Studio and Modustoolbox
A Hands-On Tutorial for generating custom models on an embedded board



#  Related resources

Resources  | Links
-----------|----------------------------------
Device documentation | [PSOC&trade; Edge MCU datasheets](https://www.infineon.com/products/microcontroller/32-bit-psoc-arm-cortex/32-bit-psoc-edge-arm#documents) <br> [PSOC&trade; Edge MCU reference manuals](https://www.infineon.com/products/microcontroller/32-bit-psoc-arm-cortex/32-bit-psoc-edge-arm#documents)
Development kits | [PSOC&trade; Edge E84 Evaluation Kit](https://www.infineon.com/KIT_PSE84_EVAL) <br> [PSOC&trade; Edge E84 AI Kit](https://www.infineon.com/KIT_PSE84_AI)
Libraries  | [mtb-dsl-pse8xxgp](https://github.com/Infineon/mtb-dsl-pse8xxgp) – Device support library for PSE8XXGP <br> [retarget-io](https://github.com/Infineon/retarget-io) – UART debug output <br> [abstraction-rtos](https://github.com/Infineon/abstraction-rtos) – FreeRTOS abstraction layer
Tools  | [ModusToolbox&trade;](https://www.infineon.com/modustoolbox) – ModusToolbox&trade; software is a collection of easy-to-use libraries and tools enabling rapid development with Infineon MCUs <br> [VSCODE;](https://code.visualstudio.com/) - The open source AI code editor


# Software setup

See [the ModusToolbox™ tools package installation guide](https://www.infineon.com/assets/row/public/documents/30/68/infineon-modustoolbox-software-installation-guide-gettingstarted-en.pdf) for information about installing and configuring the tools package.

Install a terminal emulator if you do not have one. Instructions in this document use [Tera Term](https://teratermproject.github.io/index-en.html).

Required libraries (fetched automatically via make getlibs):

retarget-io v1.9.0 – UART debug output
FreeRTOS v10.6.202 – Real-time operating system
MTB HAL – Hardware abstraction layer

# Supported kits (make variable 'TARGET')

- [PSOC&trade; Edge E84 Evaluation Kit](https://www.infineon.com/KIT_PSE84_EVAL) (`KIT_PSE84_EVAL_EPC2`) – Default value of `TARGET` (tested)
- [PSOC&trade; Edge E84 Evaluation Kit](https://www.infineon.com/KIT_PSE84_EVAL) (`KIT_PSE84_EVAL_EPC4`)
- [PSOC&trade; Edge E84 AI Kit](https://www.infineon.com/KIT_PSE84_AI) (`KIT_PSE84_AI`)


# Learning Outcomes
1. Learn and understand how to create and use tools with ModusToolbox and DEEPCRAFT Studio.
2. Understand the principles of building AI models using DEEPCRAFT Studio.
3. Be able to build custom AI models on DEEPCRAFT Studio.
4. Be able to deploy custom models to hardware boards and execute on-device inference using DEEPCRAFT Studio.


#  Steps
1. ModusToolbox&trade; and DEEPCRAFT Studio installation
2. AI Model creation on DEEPCRAFT Studio
3. Code generatation for porting a model to the board
4. Build and deploy a model to the board


## Step 1: ModusToolbox&trade; and DEEPCRAFT Studio installation

link to download ModusToolbox&trade; and DEEPCRAFT Studio
Resources  | Links
-----------|----------------------------------
ModusToolbox&trade; | [Link;](https://www.infineon.com/design-resources/development-tools/sdk/modustoolbox-software?uid=ci44510001&aid=ai4451&gclsrc=aw.ds&gad_source=1&gad_campaignid=21544549833&gbraid=0AAAAADpmf9eCeVKpUbj7qFToHJWQoXqjv&gclid=CjwKCAiAkbbMBhB2EiwANbxtbUcjLVxQyMXbMPO-9CEml5x8BNMwZ_sYdUzpfT8vvO2c3bHPpmn71RoCUbsQAvD_BwE)
DEEPCRAFT Studio | [Link;](https://developer.imagimob.com/deepcraft-studio/install-download-studio)

![ModusToolbox](images/modustoolbox.png)
**Figure 1:** ModusToolbox development environment for embedded system application design.
![DEEPCRAFT](images/deepcraft.png)
**Figure 2:** DEEPCRAFT Studio interface for AI model creation, training, and deployment.

## Step 2: AI Model creation on DEEPCRAFT Studio

### 1. Project creation on DEEPCRAFT Studio
- Open DEEPCRAFT&trade; Studio.
- New Projects
- Select Templates

![Project](images/projects.png)

You can follow more details in [DEEPCRAFT&trade;](https://developer.imagimob.com/deepcraft-studio/getting-started/starter-models-project-templates/project-template) documentation hub.

### 2. Data Collection on DEEPCRAFT Studio

![object2](images/object-2.png)

- Sensor Data Collection

![sensor](images/sensor.png)

You can follow more details in [DEEPCRAFT&trade;](https://developer.imagimob.com/deepcraft-studio/data-preparation) documentation hub.

- Image Data Collection

![sensor](images/image.png)

1. create project using object detection template in DEEPCRAFT Studio

![object1](images/object-1.png)

And you can also follow the same step as sensor data collection


### 3. Data Annotation on DEEPCRAFT Studio

In the data annotation mode, DEEPCRAFT Studio contains details in [documentation guide](https://developer.imagimob.com/deepcraft-studio/data-preparation/data-labeling) for following with more details.

- Sensor Data Annotation

here is supported sensor/sound formats - [Link](https://developer.imagimob.com/deepcraft-studio/data-preparation/bring-your-data/bring-your-own-data)

![object3](images/object-3.png)

- Image Data Annotation

here is supported Image formats - [Link](https://developer.imagimob.com/deepcraft-studio/data-preparation/bring-your-data/bring-your-own-data-object-detection)

![object4](images/object-4.png)

- Data Distribution (After compelete data annotation)

![object5](images/object-5.png)

You can follow more details in [DEEPCRAFT&trade;](https://developer.imagimob.com/deepcraft-studio/data-preparation/data-distribution) documentation hub.


### 4. Model Training on DEEPCRAFT Studio

This section provides comprehensive information on various methods to generate the model, how to initiate and monitor the training job, and the steps to download the model files from the Imagimob Cloud. And you can follow step by step in [the documentation guide](https://developer.imagimob.com/deepcraft-studio/model-training).

![object6](images/object-6.png)

### 5. Testing Model on DEEPCRAFT Studio

After you download the successfully trained model, you can verify results in DEEPCRAFT Studio.

![object7](images/object-7.png)

This sample showed the result of image/video object detection. 

## Step 3: Code generatation for porting a model to the board

After training and evaluating a model, the subsequent step is code generation. This involves converting the assessed model into executable code, which can be further optimized and deployed on edge devices. By generating the code, the logic and functionality of the model are precisely captured, facilitating the next phases of development.

You can generate optimized code for a number of different targets. And you can follow step by step in [the documentation guide](https://developer.imagimob.com/deepcraft-studio/code-generation).

![object8](images/object-8.png)

The result from code generation contains 2 files.
```
model.h
model.c
```
![object9](images/object-9.png)


## Step 4: Build and deploy a model to the board

For general information about how the [Eclipse IDE for ModusToolbox™](https://www.infineon.com/assets/row/public/documents/30/44/infineon-modustoolbox-eclipse-ide-user-guide-usermanual-en.pdf?fileId=8ac78c8c8929aa4d0189bd07dd6113f9) creates and implements projects, build and deploy.

1. create new application
2. build application
3. Modify some code (If using a custom model, which is not the sample in Modus Toolbox.)
3. deploy application


