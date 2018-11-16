Install Drive Trays
~~~~~~~~~~~~~~~~~~~

Drive trays are used to mount drives in the chassis. Each drive tray
has a status LED which is blue when active or amber if a fault has
occurred.

A tray must be placed in each drive bay to maintain proper airflow for
cooling. If fewer than twelve drives are connected, empty "air baffle"
trays must be placed in the empty bays.

A standard drive tray installation order simplifies support and is
strongly recommended:

* SSD drives for SLOG, if present

* SSD drives for L2ARC, if present

* Hard drives or SSD drives for data storage

* Air baffle filler trays to fill any remaining empty bays

Install the first drive tray in the top left drive bay. Install the
next drive tray to the right of the first. Install remaining drive
trays to the right across the row. After a row is filled with drives,
move down to the next row and start again with the left bay.

This example shows the proper order for a SLOG SSD, an L2ARC SSD,
eight hard drives, and two empty air baffle trays.

.. figure:: images/truenas/x_driveorder.png
   :width: 80%


To load an individual drive tray into a bay, press the blue button to
open the latch. Carefully slide the tray into a drive bay until the
left side of the latch touches the metal front edge of the chassis,
then gently swing the latch closed until it clicks into place.


.. figure:: images/truenas/x_driveload.png
   :width: 100%
