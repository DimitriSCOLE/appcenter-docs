.. Copyright (c) 2007-2016 UShareSoft, All rights reserved

.. _scanInstallProfile-get:

scanInstallProfile_get
----------------------

.. function:: GET /users/{uid}/scannedinstances/{siid}/scans/{sid}/installprofile

.. sidebar:: Summary

	* Method: ``GET``
	* Response Code: ``200 / 304``
	* Response Formats: ``application/xml`` ``application/json``
	* Since: ``UForge 3.4``

Retrieves the meta-data of the install profile from a scan.

Security Summary
~~~~~~~~~~~~~~~~

* Requires Authentication: ``true``
* Entitlements Required: ``migration_access``

URI Parameters
~~~~~~~~~~~~~~

* ``uid`` (required): the id of the :ref:`user-object`
* ``siid`` (required): the id of the :ref:`scannedinstance-object`
* ``sid`` (required): the id of the :ref:`scan-object`

HTTP Request Body Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

None

Example Request
~~~~~~~~~~~~~~~

.. code-block:: bash

	curl "/users/{uid}/scannedinstances/{siid}/scans/{sid}/installprofile" -X GET \
	-u USER_LOGIN:PASSWORD -H "Accept: application/xml"

.. seealso::

	 * :ref:`scannedinstance-object`
	 * :ref:`scan-object`
	 * :ref:`machinescaninstance-api-resources`
	 * :ref:`scannedInstanceScan-getAll`
	 * :ref:`scannedInstanceScan-deleteAll`
	 * :ref:`scan-multipartCreate`
	 * :ref:`scan-cancel`
	 * :ref:`scan-create`
	 * :ref:`scan-delete`
	 * :ref:`scan-get`
	 * :ref:`scan-getAll`
	 * :ref:`scanFile-getAll`
	 * :ref:`scanFileArchive-download`
	 * :ref:`scanOverlay-download`
	 * :ref:`scanOverlay-uploadChunk`
	 * :ref:`scanOverlay-upload`
	 * :ref:`scanPartition-upload`
	 * :ref:`scanPackage-getAll`
	 * :ref:`scanPackageBinary-getAll`
	 * :ref:`scanPackageFile-get`