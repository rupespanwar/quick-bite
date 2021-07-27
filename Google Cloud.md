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




