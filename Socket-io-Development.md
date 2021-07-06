# Layers
<img width="712" alt="image" src="https://user-images.githubusercontent.com/75510135/124289060-82f6d780-db6f-11eb-9363-84e026817896.png">

# Socket.io Client <=> Server communication
<img width="868" alt="image" src="https://user-images.githubusercontent.com/75510135/124372940-f43ba500-dcab-11eb-95ab-522a002c361a.png">

# Basic Chat Server & chat Client setup
<img width="1303" alt="image" src="https://user-images.githubusercontent.com/75510135/124419736-bc039780-dd7b-11eb-8be7-8cabe1f4b68f.png">


# Update DOM with latest Message 
![image](https://user-images.githubusercontent.com/75510135/124456664-9a6cd500-dda8-11eb-8278-d4eae7188eb1.png)

# Basic chat form
![image](https://user-images.githubusercontent.com/75510135/124456970-ef105000-dda8-11eb-863c-e96c206a5796.png)


## Chat form
```
<script src="/socket.io/socket.io.js"></script>
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

<style>
    input{
        width: 100%;
        height: 35px;
    }
    #messages{
        list-style-type: none;
        margin: 0;
        padding: 0;
    }
    #messages li{
        padding: 5px 10px;
    }
    #message li:nth-child(odd){
        background: #aaa;
    }
</style>

<div class="container">
    <div class="row">
        <div class="col-sm-12">
            <form id="message-form">
                <div class="col-sm-10">
                    <input id="user-message" type="text" placeholder="Enter your message" />
                </div>
                <div class="col-sm-2">
                    <input class="btn btn-primary" type="submit" value="Send!" />
                </div>
            </form>
            <ul id="messages">

            </ul>
        </div>
    </div>
</div>





```
# Create a new Namespace / admin
![image](https://user-images.githubusercontent.com/75510135/124463234-351ce200-ddb0-11eb-975d-9f967a815b69.png)





```
        # Namespace/Group Cheatsheet
        ALL these are server only

        Send an event from the server to this socket only:

        socket.emit()
        socket.send()


        Send an event from a socket to a room:

        NOTE: remember, this will not go to the sending socket

        socket.to(roomName).emit()
        socket.in(roomName).emit()


        Because each socket has it's own room, named by it's socket.id, a socket can send a message to another socket:

        socket.to(anotherSocketId).emit('hey');
        socket.in(anotherSocketId).emit('hey');


        A namespace can send a message to any room:

        io.of(aNamespace).to(roomName).emit()
        io.of(aNamespace).in(roomName).emit()


        A namespace can send a message to the entire namespace

        io.emit()
        io.of('/').emit()
        io.of('/admin').emit()
        Fullscreen


```
# Initiate NS and Room
<img width="1339" alt="image" src="https://user-images.githubusercontent.com/75510135/124527064-2707a980-de22-11eb-8991-b52139ca93ff.png">



# 1st part of the communication process, 
    - sending NS main information, 
    - send back NS information , 
    - update DOM with information
<img width="852" alt="image" src="https://user-images.githubusercontent.com/75510135/124530189-a9479c00-de29-11eb-9b50-73d4a72a3c3c.png">

<img width="1359" alt="image" src="https://user-images.githubusercontent.com/75510135/124530322-ef9cfb00-de29-11eb-983e-99936238bd68.png">


# 2nd part of the communication process, 
    - updating 2nd NS main information, 
    - send Room information , 
    - update DOM with Room information
    
 ![image](https://user-images.githubusercontent.com/75510135/124552410-220e1e80-de51-11eb-89bf-c04ca5ac9917.png)




