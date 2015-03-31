************
Shared KVP's
************

Want to create a KVP that is globally accessible to any PID? Here's how to create a shared KVP:

::

    shared.example_kvp == "foo" 

Instead of using *self*, you use *shared*.

Since shared data isn't necessarily initiated from the PID you are standing in, it's important to check that it exists before changing it:

:: 

    if shared.idle_dev_number:
        shared.idle_dev_number -= 1

Also you can treat it differently if it doesn't exist:

:: 

    if shared.idle_dev_number:
        shared.idle_dev_number -= 1
    else:
        shared.idle_dev_number = 0

Shared KVP's can be used in :doc:`../rules/registration`, as a listen_to. This way you can watch global data just like a regular KVP. 

Additionally :doc:`lists` can be used inside of shared KVP's for even more power. 


Limitations
-----------

Currently you cannot call shared KVP's from other areas, such as scripts in your libraries and workspace. This is slated to change soon though. 
