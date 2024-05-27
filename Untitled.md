old

```

    <style>

        body{

            min-height:200vh;

            position: relative;

        }

  

        .iframe-container {

            position:fixed;

            bottom:40px;

            right:0;

            background-color: aqua;

            width: 300px;

            height: 300px;

        }

        iframe {

            width: 100%;

            height: 100%;

            border: none;

        }

        .minimize-btn {

            position: absolute;

            top: 10px;

            right: 10px;

            z-index: 10;

            background: #fff;

            border: 1px solid #ccc;

            padding: 5px;

            cursor: pointer;

        }

    </style>
```

New

```
       body{

            position: relative;

        }

          .chatbot-container {

    position: fixed;

    bottom: 0.5rem;

    right: 0.5rem;

    z-index: 1;

  

    background-color: black;

    width:20rem;

    height: 20rem;

  }

  .chatbot-container > button {

    position: absolute;

    top: 1rem;

    right: 1rem;

    cursor: pointer;

  }
```