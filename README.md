# mlops-training-cairo-utm

### Prerequisites

**1. Choose or Create New Project**

- Go to your GCP console and click on this drop-down menu.
  ![Alt text](./05_Source/01_Prerequisites/01_Create_Project/01_dropdown_menu.png)
- This menu will pop up where you can create a new project or choose a project which already been created.
  ![Alt text](./05_Source/01_Prerequisites/01_Create_Project/02_create_project.png)

**2. Create a Bucket on Cloud Storage For Your Project**

- Go to your GCP console and search for **Google Storage**
  ![Alt text](./05_Source/01_Prerequisites/02_Cloud_Storage/01_GCP_Console.png)
- Click on **Create** and fill up all the bucket configuration.
  ![Alt text](./05_Source/01_Prerequisites/02_Cloud_Storage/02_create_bucket.png)
  - Pick your bucket name.
    ![Alt text](../05_Source/01_Prerequisites/02_Cloud_Storage/03_01_bucket_name.png)
  - Pick your bucket region(Recommended:us-central1).
    ![Alt text](./05_Source/01_Prerequisites/02_Cloud_Storage/03_02_bucket_region.png)
  - Pick your bucket's storage class.
    ![Alt text](./05_Source/01_Prerequisites/02_Cloud_Storage/03_03_bucket_storage_class.png)
  - Pick your bucket's access.
    ![Alt text](./05_Source/01_Prerequisites/02_Cloud_Storage/03_04_bucket_control_access.png)
  - Pick your bucket's data protection.
    ![Alt text](./05_Source/01_Prerequisites/02_Cloud_Storage/03_05_bucket_data_protection.png)
- After the bucket created, your will be redirect inside your bucket.
  ![Alt text](./05_Source/01_Prerequisites/02_Cloud_Storage/04_bucket_created.png)

**3. Enable all of the API Needed**

- Go to your GCP console and search for **Vision AI API**
  - **Enable** the **Vision AI API**
    ![Alt text](./05_Source/01_Prerequisites/03_Enable_API/01_VISION_AI_API.png)
- Go to your GCP console and search for **Cloud Natural Language API**
  - **Enable** the **Cloud Natural Language API**
    ![Alt text](./05_Source/01_Prerequisites/03_Enable_API/02_CNL_API.png)
- Go to your GCP console and search for **Cloud Speech-to-Text API**
  - **Enable** the **Cloud Speech-to-Text API**
    ![Alt text](./05_Source/01_Prerequisites/03_Enable_API/04_STT_AI_API.png)
- Go to your GCP console and search for **Vertex AI**
  - **Enable** the **Vertex AI** by clicking **ENABLE ALL RECOMMENDED APIS**
    ![Alt text](./05_Source/01_Prerequisites/03_Enable_API/03_Vertex_AI_API.png)
