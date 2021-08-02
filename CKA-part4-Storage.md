![image](https://user-images.githubusercontent.com/75510135/127826518-e1532dcc-1bfe-4f10-87ba-9bb372ee8b62.png)

# Docker Storage
![image](https://user-images.githubusercontent.com/75510135/127859162-ae5c7513-6ef1-43e7-837c-f7a9c39f9ea0.png)

![image](https://user-images.githubusercontent.com/75510135/127859236-3141db4f-37fa-403c-b202-5d54784151ee.png)
![image](https://user-images.githubusercontent.com/75510135/127859261-6ab94ce0-ee14-475d-aea2-6191e888d55c.png)

![image](https://user-images.githubusercontent.com/75510135/127859283-fc16bf1f-33fa-4c59-bda2-0c216e0be48d.png)

![image](https://user-images.githubusercontent.com/75510135/127859302-6a0fc6a1-ee8f-453c-9cfb-0e4bddb51547.png)
![image](https://user-images.githubusercontent.com/75510135/127859327-6720ca32-9438-45f9-a73b-599e5467f65e.png)
![image](https://user-images.githubusercontent.com/75510135/127859359-d797094c-96b5-469f-be79-0a87d0e0cbea.png)

![image](https://user-images.githubusercontent.com/75510135/127859392-6d612ff1-1924-4e61-8a90-4fb0d96da4f7.png)
![image](https://user-images.githubusercontent.com/75510135/127859423-de6b8424-217d-4b79-a817-504a1f8ddd50.png)
![image](https://user-images.githubusercontent.com/75510135/127859452-38cd8f3c-0c4c-4906-b4af-ec318b07e945.png)
![image](https://user-images.githubusercontent.com/75510135/127859484-ba02ea39-f473-45a1-aa61-167c7f6a8ae6.png)
![image](https://user-images.githubusercontent.com/75510135/127859504-d99c218b-ccfa-467c-a0d1-99edb4ab776e.png)
![image](https://user-images.githubusercontent.com/75510135/127859544-458c7bb3-5b31-4b9e-8a7c-b1fb1f691d90.png)
![image](https://user-images.githubusercontent.com/75510135/127859569-c29b76bc-4a78-41ef-8085-566bedb7e188.png)
![image](https://user-images.githubusercontent.com/75510135/127859705-f0216ba9-a6d4-41c3-bd79-29ca422c6e78.png)
![image](https://user-images.githubusercontent.com/75510135/127859735-d9093807-7f47-46f5-8164-81d6a11de35d.png)

# Volume Driver Plugins in Docker
![image](https://user-images.githubusercontent.com/75510135/127860028-a603b7bd-5e8a-40f8-8d94-3e05a518876c.png)

![image](https://user-images.githubusercontent.com/75510135/127860050-38a556b4-96a1-4b0e-84ce-cfd01a779e52.png)

# Container Storage Interface
![image](https://user-images.githubusercontent.com/75510135/127860105-04406556-1885-4f00-9ebe-be7914375294.png)
![image](https://user-images.githubusercontent.com/75510135/127860122-621275b0-6ef7-4697-80ee-5ee499a9beb0.png)
![image](https://user-images.githubusercontent.com/75510135/127860149-609bb7eb-bb83-4249-8088-5e5dc60b1006.png)

# Volumes
![image](https://user-images.githubusercontent.com/75510135/127863185-03ca3612-05c0-41a1-800d-40207ea74483.png)
![image](https://user-images.githubusercontent.com/75510135/127863224-41cb207c-4809-464b-92c2-7780343c180b.png)
![image](https://user-images.githubusercontent.com/75510135/127863261-38fa94e9-dd4b-4ebc-9429-54744f202069.png)
![image](https://user-images.githubusercontent.com/75510135/127863347-3d67122b-335b-4b06-bc39-0586d4087635.png)

# Persistent Volumes
![image](https://user-images.githubusercontent.com/75510135/127863426-218e3edb-b180-4999-8c90-40c1000edddc.png)
![image](https://user-images.githubusercontent.com/75510135/127863456-3072219c-e83a-4780-8b6c-960480adda3b.png)

# Persistent Volume Claims
![image](https://user-images.githubusercontent.com/75510135/127863529-8129f2c6-5294-43d5-925a-0ac51866fcc7.png)
![image](https://user-images.githubusercontent.com/75510135/127863556-0909e1f7-d0df-4406-92b6-c591fc114146.png)
![image](https://user-images.githubusercontent.com/75510135/127863581-b40a36e4-3428-44db-ac57-0069c813715c.png)
![image](https://user-images.githubusercontent.com/75510135/127863612-9bf9ee1b-d9dd-48d8-8e1c-0d92b10c4856.png)

# Using PVCs in PODs
![image](https://user-images.githubusercontent.com/75510135/127864280-e432a7be-f52c-4a3e-971f-72a295159037.png)
![image](https://user-images.githubusercontent.com/75510135/127864307-4e212a5c-cae7-40b0-97a2-1e9be4937572.png)

![image](https://user-images.githubusercontent.com/75510135/127864339-8e60fc23-8a85-4158-a27b-0ab06d84b1c0.png)



        Once you create a PVC use it in a POD definition file by specifying the PVC Claim name under persistentVolumeClaim section in the volumes section like this:


            apiVersion: v1
            kind: Pod
            metadata:
              name: mypod
            spec:
              containers:
                - name: myfrontend
                  image: nginx
                  volumeMounts:
                  - mountPath: "/var/www/html"
                    name: mypd
              volumes:
                - name: mypd
                  persistentVolumeClaim:
                    claimName: myclaim


        The same is true for ReplicaSets or Deployments. Add this to the pod template section of a Deployment on ReplicaSet.


        application stores logs at location /log/app.log. View the logs of container
        kubectl exec webapp -- cat /log/app.log

        Configure a volume to store these logs at /var/log/webapp on the host.
        apiVersion: v1
        kind: Pod
        metadata:
          name: webapp
        spec:
          containers:
          - name: event-simulator
            image: kodekloud/event-simulator
            env:
            - name: LOG_HANDLERS
              value: file
            volumeMounts:
            - mountPath: /log
              name: log-volume

          volumes:
          - name: log-volume
            hostPath:
              # directory location on host
              path: /var/log/webapp
              # this field is optional
              type: Directory

        claim some of that storage for our application. Create a Persistent Volume Claim with the given specification
        apiVersion: v1
        kind: PersistentVolume
        metadata:
          name: pv-log
        spec:
          accessModes:
            - ReadWriteMany
          capacity:
            storage: 100Mi
          hostPath:
            path: /pv/log

        Create PVC
        kind: PersistentVolumeClaim
        apiVersion: v1
        metadata:
          name: claim-log-1
        spec:
          accessModes:
            - ReadWriteOnce
          resources:
            requests:
              storage: 50Mi

        Why is the claim not bound to the available Persistent Volume?
        Access Modes Mismatch

        check capacity
        kubectl get pvc,pv

        Update the webapp pod to use the persistent volume claim as its storage.
        Replace hostPath configured earlier with the newly created PersistentVolumeClaim.
        apiVersion: v1
        kind: Pod
        metadata:
          name: webapp
        spec:
          containers:
          - name: event-simulator
            image: kodekloud/event-simulator
            env:
            - name: LOG_HANDLERS
              value: file
            volumeMounts:
            - mountPath: /log
              name: log-volume

          volumes:
          - name: log-volume
            persistentVolumeClaim:
              claimName: claim-log-1


        What is the Reclaim Policy set on the Persistent Volume pv-log
        Retain

        What would happen to the PV if the PVC was destroyed?
        The PV is not delete but not available

        kubectl delete pvc pvc-name

        The PVC is being used by a POD hence stuck in terminating

        Delete POD
        kubectl delete pod webapp
















