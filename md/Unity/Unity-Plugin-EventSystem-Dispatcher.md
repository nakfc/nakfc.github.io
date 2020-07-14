# 

资源:https://assetstore.unity.com/packages/tools/integration/event-system-dispatcher-12715
文档:http://www.ootii.com/Unity/Dispatcher/MDGuide.pdf

# 
## Dispatcher
Takes Messages and sends them
## Listener
Register Listeners
## Sender
Send Messages

## Function   
will be call
* IMessage  
    * Type
    * Sender
    * Delay
    * Data
    * IsHandled(more on this later)

    public delegate void MeeeageHandler(IMessage rMessage);


# 例子

    using UnityEngine;
    usijng System.Collections;
    using com.ootii.Messages;

    public class Sample : MonoBehaviour
    {
        void Start()
        {
            MessageDispatcher.AddListener("STARTED", OnStarted, true);
            MessageDispatcher.SendMessage(this, "STARTED", "Whoo Hool!", 0);
        }
        void OnStarted(IMessage rMessage)
        {
            Debug.Log((string)rMessage.Data);
        }
    }