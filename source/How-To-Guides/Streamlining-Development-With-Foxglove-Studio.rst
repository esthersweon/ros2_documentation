`Foxglove Studio <https://foxglove.dev/studio>`__ is an open source visualization and debugging tool for your robotics data. 
 
It is available in a variety of ways to make development as convenient as possible – it can be run as a standalone desktop app, accessed via your browser, or even self-hosted on your own domain.

View the source code on `GitHub <https://www.github.com/foxglove/studio>`__.

Installation
-------------------

To use the web app, simply open Google Chrome and navigate to `studio.foxglove.dev <https://studio.foxglove.dev>`__.

To use the desktop app for Linux, macOS, or Windows, download it directly from the `Foxglove Studio website <https://foxglove.dev/download>`__.


Connect to a data source
-------------------

On opening Foxglove Studio, you will see a dialog with a list of `all possible data sources <https://foxglove.dev/docs/studio/connection/data-sources>`__.

To connect directly to your live ROS 1 stack, click "Open connection", select the ROS 1 tab, and configure your ``ROS_MASTER_URI`` and ``ROS_HOSTNAME``.
To connect to your ROS 2 stack, click "Open connection", select the ROS 2 tab, and configure your ``ROS_DOMAIN_ID``.

You could also click "Open local file" to select any local ROS 1 ``.bag`` files or ROS 2 ``.db3`` files to load into the application.
Alternativley, you can drag-and-drop these files directly into Foxglove Studio.

To test your connection, add a `Raw Messages <https://foxglove.dev/docs/studio/panels/raw-messages>`__ panel to your `layout <https://foxglove.dev/docs/studio/layouts>`__, and see a list of available topics populate the dropdown. 
If you are not yet running any ROS nodes, you should only see the ``/rosout_agg`` topic.

Check out the `Foxglove Studio docs <https://foxglove.dev/docs/studio/connection/native>`__ for more detailed instructions.

View your ROS graph
-------------------

`Using the desktop app <https://foxglove.dev/download>`__, `connect <https://foxglove.dev/docs/studio/connection/native>`__ to your running ROS stack.
Next, add a `Topic Graph <https://foxglove.dev/docs/studio/panels/topic-graph>`__ `panel <https://foxglove.dev/docs/studio/panels/introduction>`__ to your `layout <https://foxglove.dev/docs/studio/layouts>`__.
If you've connected to your ROS stack correctly, you should now see a computational graph of your ROS nodes, topics, and services in that panel.
Use the controls on the right side of the panel to select which topics to display or to toggle services.

View your ROS params
-------------------

`Using the desktop app <https://foxglove.dev/download>`__, `connect <https://foxglove.dev/docs/studio/connection/native>`__ to your running ROS stack.
Next, add a `Parameters <https://foxglove.dev/docs/studio/panels/parameters>`__ `panel <https://foxglove.dev/docs/studio/panels/introduction>`__ to your `layout <https://foxglove.dev/docs/studio/layouts>`__.
If you've connected to your ROS stack correctly, you should now see a live view of your current ``rosparams``. 
You can edit these parameter values to publish ``rosparam`` updates back to your ROS stack.

View log messages
-------------------

To view log messages live, use the desktop app to `connect <https://foxglove.dev/docs/studio/connection/native>`__ to your running ROS stack.
To view log messages from a pre-recorded data file, you can drag-and-drop your file into either the `web <https://studio.foxglove.dev>`__ or desktop app.

Next, add a `Log <https://foxglove.dev/docs/studio/panels/log>`__ `panel <https://foxglove.dev/docs/studio/panels/introduction>`__ to your `layout <https://foxglove.dev/docs/studio/layouts>`__.
If you've connected to your ROS stack correctly, you should now see a list of your log messages, with the ability to filter them by node name or severity level.

View and manipulate your URDF model
-------------------

To visualize and control your robot model in Foxglove Studio, open the web or desktop application and add a `URDF Viewer <https://foxglove.dev/docs/studio/panels/urdf-viewer>`__ `panel <https://foxglove.dev/docs/studio/panels/introduction`__ to your `layout <https://foxglove.dev/docs/studio/layouts>`__.
Then, drag and drop your URDF file into that panel to visualize your robot model.

.. image:: foxglove-studio/urdf.png
  :width: 500 px
  :alt: Foxglove Studio's URDF Viewer panel

Select any topic publishing a `JointState`` message to update the visualization based on the published joint states (defaults to `/joint_states`).

Toggle to "Manual joint control" to set joint positions using the provided controls.

.. image:: foxglove-studio/urdf-joints.png
  :width: 500 px
  :alt: Foxglove Studio's URDF Viewer panel with editable joint positions