# Custom Training with Pre-built Container

> For more information about the topic, please refer to the presentation slides that have already been shared with you.

> Please make sure you have already done all the prerequisite tasks before continuing with this topic.

## PREPARATION

**1. Create Vertex AI Workbench**

> Do this step if you want to create a workbench. If you already have a workbench running, this steps is **optional**.

There are 2 types of workbench in Vertex AI

1. Instances

- All of the environment is already prebuilt for the user. The operating system and some other libraries in it. Users only need to choose the hardware requirements such as storage, etc.

2. User-managed Notebook

- User need to build their environment such as choosing their operating system, library installation, etc.

For this workshop, we will use **Instances**.

To create these instances, there are a few steps that need to be done.

1.  Go to your GCP console and search for **"Vertex AI"**
2.  On the left-sidebar, choose **"Workbench"**.
    <p></p>
    <p align="left" width="100%">
      <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
    </p>
    <p></p>
3.  Click on **"CREATE NEW"**
    <p></p>
    <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/02_create_workbench.png" alt="02_create_workbench.png" width="60%"/>
    </p>
    <p></p>
4.  When this menu pop-up on the right side of the page, click **"ADVANCED OPTIONS"**
    <p></p>
    <p align="left" width="100%">
      <img src="../05_Source/03_CustomTrain/01_Preparation/03_advanced.png" alt="03_advanced.png" width="40%"/>
    </p>
    <p></p>

5.  There are a few things that need to be configured before creating the instances. For the workshop here is the configuration.

    - **Details**

      - Enter your instance name
        <p></p>
        <p align="left" width="50%">
        <img src="../05_Source/03_CustomTrain/01_Preparation/04_workbench_name.png" alt="04_workbench_name.png" width="80%"/>
        </p>
        <p></p>
      - For the region, we will use us-cental1

        <p></p>
        <p align="left" width="50%">
        <img src="../05_Source/03_CustomTrain/01_Preparation/05_workbench_region.png" alt="05_workbench_region.png" width="80%"/>
        </p>
        <p></p>

      - Click **Continue**

    - **Environment**

      - For the environment, we will choose to use the latest version.

        <p></p>
        <p align="left" width="50%">
        <img src="../05_Source/03_CustomTrain/01_Preparation/06_latest_version.png" alt="06_latest_version.png" width="80%"/>
        </p>
        <p></p>

      - If you have the specific version you want to use, feel free to use the second option. - Click **Continue**

    - **Machine Type**

      - For the workshop, as the model that we use is small and only needs a small amount of computation, we will use the smallest resources provided which is **"e2-standard-2"**.

        <p></p>
        <p align="left" width="50%">
        <img src="../05_Source/03_CustomTrain/01_Preparation/07_machineType.png" alt="07_machineType.png" width="80%"/>
        </p>
        <p></p>

      - If you want to have a larger amount of computation power, you can change it here. You also can change it later after creating the instances. - Click **Continue**

    - **Disks**

      - We will use **"Balanced Persistent Disk"** for the disks.

        <p></p>
        <p align="left" width="50%">
        <img src="../05_Source/03_CustomTrain/01_Preparation/08_disk.png" alt="08_disk.png" width="80%"/>
        </p>
        <p></p>

      - Click **Continue**

    - **Networking**

      - For networking configuration, we will use the default one.

        <p></p>
        <p align="left" width="50%">
        <img src="../05_Source/03_CustomTrain/01_Preparation/09_ip.png" alt="09_ip.png" width="80%"/>
        </p>
        <p></p>

    - **IAM and security**

      - In IAM and security configuration, you can change the user access of the instances wheter it can be accessed by the **"Service Account"** or **"Single User"**.
      - For security options, make sure all of these options are enabled.

        <p></p>
        <p align="left" width="50%">
        <img src="../05_Source/03_CustomTrain/01_Preparation/12_user.png" alt="12_user.png" width="80%"/>
        </p>
        <p></p>

    - **System Health**

      - We will use default settings in this configuration.
        <p></p>
        <p align="left" width="50%">
        <img src="../05_Source/03_CustomTrain/01_Preparation/13_health.png" alt="13_health.png" width="80%"/>
        </p>
        <p></p>
      - Click **"Create"**

> It will take several minutes to create a workbench. We will use this workbench for both Custom Container and Prebuilt Container.

**2. Get Ready With the Custom Training Folder**

1. If you don't have specific folder for custom training yet. Please start with this step. If you already have the folder, process to the next step.

   - Go to Google Storage's bucket and create a new folder for your Custom Training topic.
   - Then, inside of this folder, create a folder for our data.
   - Upload **"Iris.csv"** from **"03_Custom_Training/Data"** to this data folder

2. Then, inside of this folder, create another folder for Prebuilt Container.
3. Finallay, in this folder, create another 2 folder named **"Output"** and **"Package"**

Now we can start our topic on **Custom Train Using Prebuilt Container**

## Start With Custom Train Using Prebuilt Container

### 1. Testing Training Code on the Instances.

- Go to your GCP console and search for **"Vertex AI"**
- On the left-sidebar, choose **"Workbench"**.
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- On the workbench, click on the **"OPEN JUPYTERLAB"** button.
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- Because we created prebuilt instances rather than a User-managed Notebook, we can see many kernels (environments to run the notebooks) already prepared.
  - Pytorch Kernel
  - Tensorflow Kernel
  - Python Kernel
  - etc.
    <p></p>
    <p align="left" width="100%">
      <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
    </p>
    <p></p>
- Create a folder named **"Prebuilt"** on the notebook
  - Click this icon to create a new folder.
    <p></p>
    <p align="left" width="100%">
      <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
    </p>
    <p></p>
  - Then, double-click the folder to go inside it.
- Go to material folder **"03_Custom_Training/Prebuilt_Container"** and drag & drop **""train.ipynb"** into our notebook.
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- Double-click the **"train.ipynb"** on the notebook and choose **TensorFlow 2-11** as the kernel.
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- Go to your **"Iris.csv"** in the Google Cloud Bucket and copy the gsutil URI.
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- Change this path with the copied path
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- Then go to your prebuilt container folder and copy its path by clicking this.
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- Paste it into this section of code.
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- To run all of the cells, click this button.
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- If all processes are successfully done without any problem, you will see the some folder will be created on your path you assign in the Google storage.
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
  <p></p>
  <p align="left" width="100%">
    <img src="../05_Source/03_CustomTrain/01_Preparation/01_workbench.png" alt="01_workbench.png" width="30%"/>
  </p>
  <p></p>
- As we do this just for testing code purposes, delete all of the files and folders in the output path.

### 2. Prepare the Package Files for Training.

1.  **Convert train.ipyb into train.py**

    - **Using Arg Parser**

      - This function is to makes it easy to write user-friendly command-line interfaces.
      - Let's says you want to train the ML code using another data to create another different model.
      - Instead of changing the data path, the output path and other parameter, you can assign all these things when you running your code.
        - These are the steps to do it.
          - Add new cell after the 1st cell, and copy the content of **"/03_Custom_Training/02_Prebuilt_Container/argparser.py/"** into the new cell.
          -
      - Change this snippet of code.

        > **df = pd.read_csv()** &#8594; **df = pd.read_csv(input_file)**

        > **model.save()** &#8594; **model.save(output_file)**

    - Open the terminal.
    - Change the directory to our **CustomContainer** folder.
    - Use this command to convert the ipynb file into the Python file.
      > jupyter nbconvert train.ipyb --to python
    - Rename the file into **"train.py"**
    - Before completing this process, clean up the code by deleting some snippets of code like this one
      - Remove "df"
      - Remove "test"
    - Before completing this process, test the code again to make sure the arg parser module working,

      - In the terminal, change the conda environment by running this command.
        > conda activate tensorflow
      - Then run the code using this command. Change the data_input and model_output according to your own path in Google Storage's bucket.

        > python train.py --data_input="" --model_output=""

        > Example: **python train.py --data_input="gs://trainer-mlops-cairo6557/CustomTrain/Data/Iris.csv" --model_output="gs://trainer-mlops-cairo6557/CustomTrain/PrebuiltContainer"**

    - After that, delete all of the files and folders in the output path.

2.  **Create \_\_init\_\_.py (module)**

    - First, create a folder named **"trainer"**
    - Then, move **"train.py"** into the folder
    - Go inside the folder and create an empty text file.
    - Finally, named it **"\_\_init\_\_.py"**.

3.  **Create setup.py**

    - First, drag & drop the **"setup.py"** to the **"PrebuiltContainer"** folder. You can find the **"setup.py"** in material folder **"/03_Custom_Training/02_Prebuilt_Container/"**
    - In **"setup.py"**, there are code segment **REQUIRED_PACKAGES**. In this section, you will put any library that you want to use for the training code.
    - However, because we will use prebuilt model which already installed with tensorflow, we don't need to put tensorflow library on the **REQUIRED_PACKAGES**. We will put **"gcsfs"** library as we will use it.

4.  **Create the package**

    - To create a package, all of the previous steps must be completed.
    - In the material folder **"/03_Custom_Training/02_Prebuilt_Container/"**, there a text file named **"build_package.txt"**.
    - Copy content of this text file and paste it into terminal.
    - If the process successful, there will be 2 folders created which is **"dist"** which contains the package file and **"trainer.egg-info"**

5.  **Copy the package file into the Google Storage**

    - Next, you will need copy the package file into the Google Cloud Storage.

      - In terminal, change directory to **"dist"** folder by running this code.
        > cd dist/
      - To copy the package file, run this command. Change the **PACKAGE_NAME** and the **PACKAGE_FOLDER_OUTPUT** with your own path.

        > gsutil cp {**PACKAGE_NAME**} {**PACKAGE_FOLDER_OUTPUT**}

        > Example: gsutil cp trainer-0.2.tar.gz gs://trainer-mlops-cairo6557/CustomTrain/PrebuiltContainer/package

### 3. Train the model using Prebuilt container

- Go to your GCP console and search for **"Vertex AI"**
- On the left-sidebar, choose **"Training"** and click on **"TRAIN NEW MODEL"**
- The training steps for custom training are slightly the same as training using AutoML.
- These are the training steps for custom training using prebuilt containers.

  1.  **Training Method**
      - As we prepare the dataset ourselves and do not use the dataset features in the Vertex AI, we will select "No Managed Dataset" on the **dataset option**.
      - As for the **Model training method**, we will choose the custom training.
      - Click **"Continue"**
  2.  **Model Details**

      - In this tab, we will choose **"train new model"**.
      - If you want to train a new version of an existing model, choose the other option as you can do a performance comparison between different versions of the model.
      - Then, input the name of your model.
      - Click **"Continue"**

  3.  **Training Container**

      - For this option, we will choose **"Prebuilt Container"**.

      - For **Model Framework**, choose **"Tensorflow"**

      - For **Model Framework Version**, choose same as your kernel version where you test the training code before which is **"2.11"**.

      - In **Pre-built container settings**
        - For **Package Location**, choose the package that we copy to cloud storage before.
        - For **Python Module**, insert **"trainer.train"**
          - **"trainer"** is the name of folder that we used to create the package.
          - **"train"** is the name of python file inside the python trainer.
      - For **Arguments**, copy content from **"/03_Custom_Training/02_Prebuilt_Container/arg_train.txt"** and paste it into the field.

        - Change **"[DATA_PATH_IN_GS]"** with your data path in the Google Cloud Storage.

          > **EXAMPLE: --data_input="gs://trainer-mlops-cairo6557/CustomTrain/Data/Iris.csv"**

        - Change **"[OUTPUT_PATH_IN_GS]"** with your output path in the Google Cloud Storage.

          > **EXAMPLE: --model_output="gs://trainer-mlops-cairo6557/CustomTrain/PrebuiltContainer/output"**

      - Click **"Continue"**

  4.  **Hyperparameter**
      - In this section, you can adjust the hyperparameter for your training.
      - It will train multiple model using the range of parameter that we all ready set. Then it will choose the model with best performance.
      - However, we will not enable it.
      - Click **"Continue"**.
  5.  **Compute and Pricing**
      - In this section, as for the **Region**, we will use **"us-central1"**.
      - As for the **Machine Type**, we will only use **"n1-standard-4"** as we only need lower compute power
      - As for the **Accelerator Type**, we will choose nothing.
        - If your training code needs to use GPU, you can choose what GPU you want for your training container.
      - As for the **Disk Type**, we will use **"Standard Persistent Disk"**.
      - As for the **Disk Size**, we will use **"100GB"** as it the lowest size we can choose.
      - Click **"Continue"**.
  6.  **Prediction container**
      - As we don't have any prediction container, we will choose the **"No Prediction Container"** option.
        - If you have your prediction container, maybe you want to make some processing on the result of the model, you can push your prediction image into the the artifact registry.
      - Click **"Start Training"**.

- Check the bucket after the training is done to ensure the models are there.

  > This training only will take a few minutes. Stay tuned!

### 4. Deploy the Trained Model to an Endpoint.

- When the training process already done, you will see your model exported into your output path you already choose.
- However, in contrast to the AutoML method, the model does not register to the model registry automatically.
- Therefore, before we can deploy the trained model into an endpoint, we must register it first.
- This is the steps of registering the model into Model Registry.

  1. Go to your GCP console and search for **"Vertex AI"**
  2. On the left-sidebar, choose **"Model Registry"** and click on **"IMPORT"**
  3. There are a few configuration sections you need to choose.
     1. **Name and region**
        - This depends on you. If your model is a new version of the previous ML model, you can choose **"Import as new version"**.
        - However, for this workshop, as we don't have a previous version of the ML model, we will choose **"Import as new model"**.
        - Input the name for your model
        - Choose **Region** for your model. We will choose **"us-central1"**.
     2. **Model Settings**
        - As we don't have a prebuilt deployment container for our model, we will choose **"Import model artifacts into a new pre-built container"**.
        - In **Pre-built container settings**
          - **Model Framework**
            - We will choose **"sci-kit-learn"** because we used this framework for our ML model.
          - **Model Framework Version**
            - We will choose **"0.24"**. This is because for our training, we use this version too. It is better to use the same version for training and deployment.
          - **Model Artifact Location**
            - Click **"Browse"** and choose the path of your ML model you want to register into the Model Registry.
     3. **Explainability**
        - The explanation of these features already explained in the AutoML section.
        - Click **IMPORT** to continue

- After this, you can deploy your trained model into the endpoint.

  - Search for **Vertex AI** on the GCP search tab
  - On the left-sidebar, choose **"Model Registry"**.
  - Your model should be shown there.
      <p></p>
      <p align="left" width="100%">
        <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/01_modelRegistry.png" alt="01_modelRegistry" width="60%"/>
      </p>
      <p></p>
  - Click on the model to go to the model information page.
      <p></p>
      <p align="left" width="100%">
        <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/02_model_info.png" alt="02_model_info" width="60%"/>
      </p>
      <p></p>
  - On this page, you can check all the information about your model
    - **Precision**
      - The percentage of predictions that were correct (positive). The higher the precision, the fewer false positives predicted.
    - **Recall**
      - The percentage of all ground truth items that were successfully predicted by the model. The higher the recall, the fewer false negatives, or the fewer predictions missed.
    - **Precision-Recall Curve**
      - Trade-off between precision and recall at different confidence thresholds. A lower threshold results in higher recall but typically lower precision, while a higher threshold results in lower recall but typically with higher precision.
    - **Precision-Recall By Threshold**
      - Model performance on the top-scored label along the full range of confidence threshold values. A higher confidence threshold produces fewer false positives, which increases precision. A lower confidence threshold produces fewer false negatives, which increases recall.
    - **Confusion Matrix**
      - It represents the prediction summary in matrix form. It shows how many predictions are correct and incorrect per class. It helps in understanding the classes that are being confused by the model as other classes.
  - So to use the model for deployment, we need to create the endpoint first.

    - So here are the steps to create an endpoint:

      1.  Click on **"Deploy & Test"**, and then click **"DEPLOY TO ENDPOINT"**.
          <p></p>
          <p align="left" width="100%">
            <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/03_create_endpoint.png" alt="03_create_endpoint" width="80%"/>
          </p>
          <p></p>
      2.  There will be 2 configiration bar on the endpoint creation page.

          1.  **Define Your Endpoint**
              - There are 2 choices here. -
                - **Create a new endpoint** - If you don't have or you want to create a new endpoint, choose this.
                - **Use existing endpoint** - If you already have an endpoint and want to use it, choose this.
                - Then, choose the name for your endpoint.
                  <p></p>
                  <p align="left" width="100%">
                  <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/04_create_endpoint_name.png" alt="04_create_endpoint_name" width="60%"/>
                  </p>
                  <p></p>
          2.  **Model Settings**

              - **Traffic Split**

                - If you have multiple versions of the model running on one endpoint, you can split the traffic between them.
                - For example, if you want to test the deployment model performance on live data using blue/green deployment or Canary deployment, this splitting method can be helpful.
                  <p></p>
                  <p align="left" width="100%">
                  <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/05_traffic_split.png" alt="05_traffic_split" width="60%"/>
                  </p>
                  <p></p>

              - **Number of compute nodes**

                - If you want to deploy several versions of the ML Model on one endpoint, you will need to increase your number of compute nodes.
                - However, for this training, as we only deploy 1 model, we will put the minimum amount of compute nodes which is 1.
                  <p></p>
                  <p align="left" width="100%">
                  <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/06_compute_nodes.png" alt="06_compute_nodes" width="60%"/>
                  </p>
                  <p></p>

              - **Enable access logging for this endpoint**
                - You can also enable logging for your endpoint.
                - Things like request per second, prediction error percentage, latency, and many more will be recorded for future analysis.
                - If you are currently in production, you might want to leave this option enabled.
                - However, because we currently learning, I will disable this option.
                  <p></p>
                  <p align="left" width="100%">
                  <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/07_access_loggin.png" alt="07_access_loggin" width="60%"/>
                  </p>
                  <p></p>

  > The deployment and endpoint creation will take some time about 5-10 minutes.

### 5. Testing the Endpoint.

For using the endpoint, there are some ways to do it.

- You can test your model on the model information page.

  - At the **"Deploy & Test"** tab, you can input your data in JSON format.
  - You can use the test set that is already prepared in the material folder **"/03_Custom_Training/01_Custom Container/Test/Sample/INPUT-JSON"**
  - Copy the content, paste it on the input section and click **"Predict"**
  - You will get the result like this.
    <p></p>
    <p align="left" width="100%">
    <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/09_result_test.png" alt="09_result_test" width="80%"/>
    </p>
    <p></p>

- However, if you want to use this endpoint embedded in your code, these are the steps.

  - At "Deploy & Test" tab, click **"Sample Request"**
     <p></p>
     <p align="left" width="100%">
     <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/10_sample_request.png" alt="10_sample_request" width="80%"/>
     </p>
     <p></p>

  - There will be 2 way of connecting to the endpoint which is through raw API or using Python Code.
     <p></p>
     <p align="left" width="100%">
     <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/11_2way.png" alt="11_2way" width="80%"/>
     </p>
     <p></p>
     - For raw API, you can just follow the instructions given in the tab.

    - For Python code, here are the instructions.
      1.  You will need a Python module for connection which you can get from [HERE]("https://github.com/googleapis/python-aiplatform/blob/main/samples/snippets/prediction_service/predict_image_classification_sample.py). However, it will be no need for you to that as I already prepare the python code and the sample image in the material folder.
      2.  Open your Google cloud shell and upload **"03_Custom_Training/01_Custom Container/Test/Code/"** folder into it.
          <p></p>
          <p align="left" width="100%">
          <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/12_upload_code.png" alt="12_upload_code" width="80%"/>
          </p>
          <p></p>
      3.  Open the editor and open the **"request_api.py"**.
          1. Copy this code snippet from **Sample Request**.
             <p></p>
             <p align="left" width="100%">
             <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/13_copy_request.png" alt="13_copy_request" width="80%"/>
             </p>
             <p></p>
          2. Paste it here at the bottom of the Python file.
             <p></p>
             <p align="left" width="100%">
             <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/14_paste_request.png" alt="14_paste_request" width="80%"/>
             </p>
             <p></p>
      4.  Feel free to change the parameter of the **"instances"**
      5.  After all is complete, go back to the cloud shell.
          1. If you get error saying there are no module **"aiplatform"**, you will need to install aiplatform Python Library first. Run this command to install it.
             > pip install google-cloud-aiplatform
          2. Change the directory to your **"request_api.py"**
          3. Run the Python code by using this command.
             > python request_api.py
      6.  You will get the result like this.
          <p></p>
          <p align="left" width="100%">
          <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/15_result.png" alt="15_result" width="80%"/>
          </p>
          <p></p>

---

- If you are not using the endpoint, it will be recommended to delete it as you will be charged hourly.
- Here are the steps to delete an endpoint.
  - You will need to undeployed the model first.
    - Search for **Vertex AI** on the GCP search tab
    - On the left-side navbar, choose **"Online Prediction"** and choose the endpoint you want to close.
      <p></p>
      <p align="left" width="100%">
        <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/16.png" alt="16" width="40%"/>
      </p>
      <p></p>
    - Click on the 3 dots at the end of the model information and choose **"Undeploy model from endpoint"**
      <p></p>
      <p align="left" width="100%">
      <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/17.png" alt="17" width="100%"/>
      </p>
      <p></p>
    - Go back and click on the 3 dots again and choose **"Delete endpoint"**
      <p></p>
      <p align="left" width="100%">
      <img src="../05_Source/03_AutoML/01_ImageClassification/04_ModelDeployment/18.png" alt="18" width="100%"/>
      </p>
      <p></p>
