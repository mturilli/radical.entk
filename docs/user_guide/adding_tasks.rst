.. _uguide_add_tasks:


************
Adding Tasks
************

In this section, we show how we can add more tasks to our base script from the :ref:`Getting Started <uguide_get_started>` section.

.. note:: The reader is assumed to be familiar with the :ref:`PST Model <overview>` and to have read through the :ref:`introduction` of Ensemble Toolkit.

.. note:: This chapter assumes that you have successfully installed Ensemble Toolkit, if not see :ref:`Installation`.

You can download the complete code discussed in this section :download:`here <../../examples/user_guide/add_tasks.py>` or find it in 
your virtualenv under ``share/radical.entk/user_guide/scripts``.        

Below, you can see the code snippet that shows how you can create more Task objects
and **add** them to the Stage using the **add_task()** method.

.. literalinclude:: ../../examples/user_guide/add_tasks.py
    :language: python
    :dedent: 4
    :linenos:15-27

.. code-block:: python

    for cnt in range(10):
        t = Task()                          # Create a Task object
        t.name = 'my-task'                  # Assign a name to the task (optional)
        t.executable = ['/bin/echo']        # Assign executable to the task   
        t.arguments = ['I am task %s'%cnt]  # Assign arguments for the task executable

        # Add the Task to the Stage
        s.add_tasks(t)

To run the script, execute the following from the command line:

.. tip:: We set up a MongoDB server for this guide. You can run the following command to use it
        ``export RADICAL_PILOT_DBURL="mongodb://138.201.86.166:27017/ee_exp_4c"``

.. code-block:: bash

    python add_tasks.py


Let's take a look at the complete code of the example. You can generate a more verbose output by setting the environment
variable ``RADICAL_ENTK_VERBOSE=DEBUG``.

.. literalinclude:: ../../examples/user_guide/add_tasks.py
