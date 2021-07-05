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


