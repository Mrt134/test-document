.. index:: VAAI
.. _VAAI:

VAAI
====

VMware's vStorage APIs for Array Integration, or *VAAI*, allows
storage tasks such as large data moves to be offloaded from the
virtualization hardware to the storage array. These operations are
performed locally on the NAS without transferring bulk data over the
network.


.. index:: VAAI for iSCSI
.. _VAAI_for_iSCSI:

VAAI for iSCSI
--------------

VAAI for iSCSI supports these operations:

* *Atomic Test and Set* (*ATS*) allows multiple initiators to
  synchronize LUN access in a fine-grained manner rather than locking
  the whole LUN and preventing other hosts from accessing the same LUN
  simultaneously.

* *Clone Blocks* (*XCOPY*) copies disk blocks on the NAS. Copies occur
  locally rather than over the network. The operation is similar to
  `Microsoft ODX
  <https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831628(v=ws.11)>`__.

* *LUN Reporting* allows a hypervisor to query the NAS to determine
  whether a LUN is using thin provisioning.

* *Stun* pauses virtual machines when a pool runs out of
  space. The space issue can then be fixed and the virtual machines
  can continue rather than reporting write errors.

* *Threshold Warning* the system reports a warning when a
  configurable capacity is reached. In %brand%, this threshold is
  configured at the pool level when using zvols
  (see :numref:`Table %s <iscsi_targ_global_config_tab>`)
  or at the extent level
  (see :numref:`Table %s <iscsi_extent_conf_tab>`)
  for both file and device based extents. Typically, the warning is
  set at the pool level, unless file extents are used, in which case
  it must be set at the extent level.

* *Unmap* informs %brand% that the space occupied by deleted files
  should be freed. Without unmap, the NAS is unaware of freed space
  created when the initiator deletes files. For this feature to work,
  the initiator must support the unmap command.

* *Zero Blocks* or *Write Same* zeros out disk regions. When
  allocating virtual machines with thick provisioning, the zero write
  is done locally, rather than over the network. This makes virtual
  machine creation and any other zeroing of disk regions much quicker.
