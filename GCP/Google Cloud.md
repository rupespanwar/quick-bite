# GKE creation steps for new Google Cloud UI


    Click the Hamburger menu on the top left-hand side of the dashboard.

    Click Kubernetes Engine


    Click the ENABLE button to enable the Kubernetes API for this project.

    After a few minutes of waiting, clicking the bell icon in the top right part of the menu should show a green checkmark for Enable services: container.googleapis.com


    If you refresh the page it should show a screen to create your first cluster. If not, click the hamburger menu and select Kubernetes Engine and then Clusters.
    Once you see the screen below, click the CREATE button.


    A Create Cluster dialog will open and provide two choices. Standard and Autopilot. Click the CONFIGURE button within the Standard cluster option

    A form similar to the one shown in the video will be presented. Set the Name to multi-cluster (step 1). Confirm that the Zone set is actually near your location (step 2). The Node Pool that is discussed in the video is now found in a separate dropdown on the left sidebar. Click the downward-facing arrow to view the settings. No changes are needed here (step 3). Finally, click the CREATE button at the bottom of the form (step 4).


    After a few minutes, the cluster dashboard should load and your multi-cluster should have a green checkmark in the table.



# Generate a Service Account.

    Click the Hamburger menu on the top left-hand side of the dashboard, find IAM & Admin, and select Service Accounts. Then click the CREATE SERVICE ACCOUNT button.

    In the form that is displayed, set the Service account name to travis-deployer (step 1), then click the CREATE button (step 2).

    Click in the Select a role filter and scroll down to select Kubernetes Engine and then Kubernetes Engine Admin.


    Make sure the filter now shows Kubernetes Engine Admin and then click CONTINUE

    The Grant users access form is optional and should be skipped. Click the DONE button.

    You should now see a table listing all of the service accounts including the one that was just created. Click the three dots to the right of the service account you just created. Then select Manage Keys in the dropdown.

    In the Keys dashboard, click ADD KEY and then select Create new key.

    In the Create private key dialog box, make sure Key type is set to JSON, and then click the CREATE button.

    The JSON key file should now download to your computer.
