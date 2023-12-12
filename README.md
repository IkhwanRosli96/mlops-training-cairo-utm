# mlops-training-cairo-utm

### Prerequisites

**1. Choose or Create New Project**

- Go to your GCP console and click on this drop-down menu.
  <p></p>
  <p align="left" width="100%">
    <img src="./05_Source/01_Prerequisites/01_Create_Project/01_dropdown_menu.png" alt="01_dropdown_menu" width="70%"/>
  </p>
  <p></p>
- This menu will pop up where you can create a new project or choose a project which already been created.
  <p></p>
  <p align="left" width="100%">
    <img src="./05_Source/01_Prerequisites/01_Create_Project/02_create_project.png" alt="02_create_project" width="40%"/>
  </p>
  <p></p>

**2. Create a Bucket on Cloud Storage For Your Project**

- Go to your GCP console and search for **Google Storage**
  <p></p>
  <p align="left" width="100%">
    <img src="./05_Source/01_Prerequisites/02_Cloud_Storage/01_GCP_Console.png" alt="01_GCP_Console" width="40%"/>
  </p>
  <p></p>

- Click on **Create** and fill up all the bucket configuration.
  <p></p>
  <p align="left" width="100%">
    <img src="./05_Source/01_Prerequisites/02_Cloud_Storage/02_create_bucket.png" alt="02_create_bucket" width="40%"/>
  </p>
  <p></p>
- This is the recommended settings for Cloud Storage's bucket for the workshop.
  - Pick your bucket name.
    <p></p>
    <p align="left" width="100%">
      <img src="./05_Source/01_Prerequisites/02_Cloud_Storage/03_01_bucket_name.png" alt="03_01_bucket_name" width="40%"/>
    </p>
    <p></p>
  - Pick your bucket region(Recommended:us-central1).
    <p></p>
    <p align="left" width="100%">
      <img src="./05_Source/01_Prerequisites/02_Cloud_Storage/03_02_bucket_region.png" alt="03_02_bucket_region" width="40%"/>
    </p>
    <p></p>
  - Pick your bucket's storage class.
    <p></p>
    <p align="left" width="100%">
      <img src="./05_Source/01_Prerequisites/02_Cloud_Storage/03_03_bucket_storage_class.png" alt="03_03_bucket_storage_class" width="40%"/>
    </p>
    <p></p>
  - Pick your bucket's access.
    <p></p>
    <p align="left" width="100%">
      <img src="./05_Source/01_Prerequisites/02_Cloud_Storage/03_04_bucket_control_access.png" alt="03_04_bucket_control_access" width="40%"/>
    </p>
    <p></p>
  - Pick your bucket's data protection.
    <p></p>
      <p align="left" width="100%">
        <img src="./05_Source/01_Prerequisites/02_Cloud_Storage/03_05_bucket_data_protection.png" alt="03_05_bucket_data_protection" width="40%"/>
      </p>
      <p></p>
  - After the bucket created, your will be redirect inside your bucket.
    <p></p>
    <p align="left" width="100%">
      <img src="./05_Source/01_Prerequisites/02_Cloud_Storage/04_bucket_created.png" alt="04_bucket_created" width="40%"/>
    </p>
    <p></p>

**3. Enable all of the API Needed**

- Go to your GCP console and search for **Vision AI API**
  - **Enable** the **Vision AI API**
  - <p></p>
    <p align="left" width="100%">
      <img src="./05_Source/01_Prerequisites/03_Enable_API/01_VISION_AI_API.png" alt="01_VISION_AI_API" width="60%"/>
    </p>
    <p></p>
- Go to your GCP console and search for **Cloud Natural Language API**
  - **Enable** the **Cloud Natural Language API**
    <p></p>
    <p align="left" width="100%">
      <img src="./05_Source/01_Prerequisites/03_Enable_API/02_CNL_API.png" alt="02_CNL_API" width="60%"/>
    </p>
    <p></p>
- Go to your GCP console and search for **Cloud Speech-to-Text API**
  - **Enable** the **Cloud Speech-to-Text API**
    <p></p>
    <p align="left" width="100%">
      <img src="./05_Source/01_Prerequisites/03_Enable_API/04_STT_AI_API.png" alt="04_STT_AI_API" width="60%"/>
    </p>
    <p></p>
- Go to your GCP console and search for **Vertex AI**
  - **Enable** the **Vertex AI** by clicking **ENABLE ALL RECOMMENDED APIS**
    <p></p>
    <p align="left" width="100%">
      <img src="./05_Source/01_Prerequisites/03_Enable_API/03_Vertex_AI_API.png" alt="03_Vertex_AI_API" width="60%"/>
    </p>
    <p></p>
