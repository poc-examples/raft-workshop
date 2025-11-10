### Accessing the OpenShift Console

1. **Open** [**OpenShift Console**](https://console-openshift-console.apps.service-cbe-3.bkhx.p1.openshiftapps.com)

   ![Login Options](Image/1.png)

   → Select **openshift** as your login option.

---

2. **Click “Log in with openshift”** to continue.

   ![Login with OpenShift](Image/2.png)

---

3. **Enter your credentials** and click **Sign In**.

   ![Sign In](Image/3.png)

---

4. **Register a new user** if you don’t already have one.

   ![Register Page](Image/4.png)

---

5. **After logging in, skip the tour or click “Get started”** to explore the Developer Console.

   ![Welcome Screen](Image/5.png)

---
6. **From the left menu, select “+Add”** to view getting started options.

   ![Add Menu](Image/6.png)

---

7. **Click the grid icon** on the top bar to access available OpenShift applications.

   ![OpenShift Menu](Image/7.png)

---

8. **Select “Red Hat OpenShift AI”** from the dropdown menu.

   ![Select OpenShift AI](Image/8.png)

---

9. **Click “Log in with OpenShift”** to authenticate your access.

   ![Login with OpenShift AI](Image/9.png)

---

10. **Choose “openshift” as the login provider**.

   ![Select OpenShift Login](Image/10.png)

---

11. **Once logged in, navigate to “Data Science Projects.”**

   ![Data Science Projects Home](Image/11.png)

---

12. **Click “Create a project”** to start setting up your workspace.

   ![Create Project](Image/12.png)

---

13. **Enter your project name** (e.g., `arahmani-workshop`) and click **Create**.

   ![Enter Project Details](Image/13.png)

---

14. **Your new project is created.**  
   Review available sections like **Workbenches** and **Pipelines**.

   ![Project Overview](Image/14.png)

---

15. **Go to the “Workbenches” tab** to start building your development environment.

   ![Workbench Tab](Image/15.png)

---

16. **Click “Create workbench”** to start setting up your Jupyter environment.

   ![Create Workbench](Image/16.png)

---

17. **Select the workbench image** from the dropdown list.  
   Choose **Jupyter | Data Science | CPU | Python 3.12** for this setup.

   ![Workbench Image Selection](Image/17.png)

---

18. **Specify deployment settings.**  
   Choose **Small** container size and ensure **Cluster storage** is configured with default settings.

   ![Deployment Size](Image/18.png)

---

19. **Review the configuration summary** — including Environment Variables, Storage, and Connections.

   ![Workbench Configuration Summary](Image/19.png)

---

20. **Click “Create connection”** under the *Connections* section to add object storage integration.

   ![Create Connection](Image/20.png)

---

21. **Select “S3 compatible object storage – v1”** as the connection type.  
   This enables integration with S3-compatible storage such as MinIO.

   ![Select S3 Connection Type](Image/21.png)

---

22. **Enter the connection details.**  
   Fill in the following fields:
   - **Connection name:** `arahmani-connection`  
   - **Access key:** `minioadmin`  
   - **Secret key:** *(your MinIO secret key)*

   ![Connection Details Part 1](Image/22.png)

---

23. **Complete the connection setup** by adding:
   - **Endpoint:** `http://minio-api.minio-operator.svc.cluster.local:9000`  
   - **Bucket:** `test`

   ![Connection Details Part 2](Image/23.png)

---

24. **Verify the connection appears under the Connections list.**  
   Ensure your new S3-compatible connection is active and attached.

   ![Connection Verified](Image/24.png)

---

25. **Return to the Workbenches tab.**  
   Your new workbench (`arahmani-workbench`) should now show status **Starting**, and then **Running** once ready.

   ![Workbench Running](Image/25.png)
---

26. **Open your running workbench** by clicking on its name.  
    This launches your JupyterLab environment inside Red Hat OpenShift AI.

    ![Workbench Launcher](Image/26.png)

---

27. **In JupyterLab**, you can see available options such as:
    - **Notebook (Python 3.12)**  
    - **Console (Python 3.12)**  
    - **Elyra Pipeline Editor**  
    - **Terminal and Text File options**

    ![JupyterLab Home](Image/27.png)

---

28. **Open a new terminal** and clone the RAFT workshop repository using:  
    ```bash
    git clone https://github.com/poc-examples/raft-workshop.git
    ```

    ![Git Clone Command](Image/28.png)

---

29. **Verify the cloned repository** appears in your workspace.  
    The folder `raft-workshop` should include the following files:
    - `1-generate-data.ipynb`  
    - `2-push-dataset.ipynb`  
    - `3-finetune.ipynb`  
    - `4-eval.ipynb`  
    - `config.env`  
    - `setup_raft.sh`  
    - `sample_data/`

    ![Repository Contents](Image/29.png)

---

30. **Open and edit the `config.env` file.**  
    Update the `DATASCIENCE_PROJECT_NAMESPACE` field with your project name (e.g., `arahmani-workshop`).

    Example:
    ```bash
    DATASCIENCE_PROJECT_NAMESPACE = "arahmani-workshop"
    ```

    ![Config File Update](Image/30.png)
