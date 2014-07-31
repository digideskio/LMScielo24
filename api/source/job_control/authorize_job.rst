Authorize Job
=============

Authorizes an existing job. If your account has the “customer authorization” feature enabled
(It is not enabled by default.) jobs you create will be held in the “Authorizing” state until
you call this method. Calling this method on a job that is not the “Authorizing” state has no
effect and will return success.

**HTTP Method**

.. http:get:: /api/job/authorize

**Query String Parameters** - Required

+------------------+------------------------------------------------------------------------------+
| Name             | Details                                                                      |
+==================+==================+===========================================================+
| v                | `Description`    | The version of the API to use                             |
|                  +------------------+-----------------------------------------------------------+
|                  | `Allowed Values` | 1-                                                        |
|                  +------------------+-----------------------------------------------------------+
|                  | `Example`        | ``v=1``                                                   |
+------------------+------------------+-----------------------------------------------------------+
| api_token        | `Description`    | The API token used for this session                       |
|                  +------------------+-----------------------------------------------------------+
|                  | `Allowed Values` | Hex String                                                |
|                  +------------------+-----------------------------------------------------------+
|                  | `Example`        | ``api_token=7ca5dc5c7cce449fb0fff719307e8f5f``            |
+------------------+------------------+-----------------------------------------------------------+
| job_id           | `Description`    | The id of the job to be authorized                        |
|                  +------------------+-----------------------------------------------------------+
|                  | `Allowed Values` | Hex String                                                |
|                  +------------------+-----------------------------------------------------------+
|                  | `Example`        | ``job_id=64bea283eff6475ea6596027a6ba0929``               |
+------------------+------------------+-----------------------------------------------------------+

**Responses**

+-----------+------------------------------------------------------------------------------------------+
| HTTP Code | Details                                                                                  |
+===========+===============+==========================================================================+
| 204       | `Description` | Success                                                                  |
|           +---------------+--------------------------------------------------------------------------+
|           | `Contents`    | none                                                                     |
+-----------+---------------+--------------------------------------------------------------------------+
| 400       | `Description` | An error occurred                                                        |
|           +---------------+--------------------------------------------------------------------------+
|           | `Contents`    | .. code-block:: javascript                                               |
|           |               |                                                                          |
|           |               |  {                                                                       |
|           |               |    "ErrorType": "ERROR_TYPE_ENUM",                                       |
|           |               |    "ErrorComment": "Description of error details.                        |
|           |               |     See Error Output Format."                                            |
|           |               |  }                                                                       |
+-----------+---------------+--------------------------------------------------------------------------+

**Example Requests**

    .. sourcecode:: http

        GET /api/job/authorize?v=1&api_token=7ca5dc5c7cce449fb0fff719307e8f5f HTTP/1.1
            &job_id=64bea283eff6475ea6596027a6ba0929
        Host: api.cielo24.com

**Example Response**

    .. sourcecode:: http

        HTTP/1.1 204 OK
        Content-Type: text/javascript

        none