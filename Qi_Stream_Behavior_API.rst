QiStream Behavior API calls
==================

The API calls in this section are all used to create and manipulate QiStream behaviors. See .. _Qi Types: https://github.com/osisoft/Qi-Docs/blob/Qi_Edits/docs/Qi_Types.rst for a list of supported QiTypes, a discussion of compound indexes, and general information about QiTypes. 


``DeleteBehavior()``
----------------

Deletes a QiStream behavior from the specified namespace that matches the specified behaviorId.


**Syntax**

::

    void DeleteBehavior(string tenantId, string namespaceId, string behaviorId);
    Task DeleteBehaviorAsync(string tenantId, string namespaceId, string behaviorId);

**Http**

::

    DELETE Qi/{tenantid}/{namespaceId}/Behaviors/{behaviorId}

**Parameters**

``string tenantID``
  The tenant identifier for the request
``string namespaceId``
  The namespace identifier for the request
 
``behaviorId``
  The ID of the behavior to delete; the behavior must not be associated with any streams.

**Optional parameters**

  None
  
**Returns**
  A QiStream object for the specified typeId and namespace

Security
  Allowed by administrator accounts

**********

``GetBehavior()``
----------------

Retrieves a QiStream behavior from the specified namespace that matches the specified behaviorId.


**Syntax**

::

    QiStreamBehavior GetBehavior(string tenantId, string namespaceId, string behaviorId);
    Task<QiStreamBehavior> GetBehaviorAsync(string tenantId, string namespaceId, string behaviorId);

**Http**

::

    GET Qi/{tenantId}/{namespaceId}/Behaviors/{behaviorId}

**Parameters**

``string tenantID``
  The tenant identifier for the request
``string namespaceId``
  The namespace identifier for the request
``behaviorId``
  The ID of the behavior to retrieve.

**Optional parameters**

  None
  
**Returns**
  A QiStream object

Security
  Allowed by administrator and user accounts

**********

``GetBehaviors()``
----------------

Retrieves all QiStream behaviors from a namespace.


**Syntax**

::

    IEnumerable<QiStreamBehavior> GetBehaviors(string tenantId, string namespaceId);
    Task<IEnumerable<QiStreamBehavior>> GetBehaviorsAsync(string tenantId, string namespaceId);

**Http**

::

    GET Qi/{tenantId}/{namespaceId}/Behaviors

**Parameters**

``string tenantID``
  The tenant identifier for the request
``string namespaceId``
  The namespace identifier for the request
``behaviorId``
  The ID of the behavior to retrieve.

**Optional parameters**

  None
  
**Returns**
  An IEnumerable of all behavior objects

Security
  Allowed by administrator and user accounts

  
**********

``GetOrCreateBehavior()``
----------------

Retrieves the QiStream behavior from a namespace, or creates the behavior if the  behavior does not already exist. If the bahavior exists, it is returned to the caller unchanged.

**Syntax**

::

    QiStreamBehavior GetOrCreateBehavior(string tenantId, string namespaceId, QiStreamBehavior entity);
    Task<QiStreamBehavior> GetOrCreateBehaviorAsync(string tenantId, string namespaceId, QiStreamBehavior entity);

**Http**

::

    POST  Qi/{tenantId}/{namespaceId}/Behaviors
	
**Parameters**

``string tenantID``
  The tenant identifier for the request
``string namespaceId``
  The namespace identifier for the request
``entity``
  A QiStreamBehavior object to add to Qi.

**Optional parameters**

  None
  
**Returns**
  An IEnumerable of all behavior objects

Security
  Allowed by administrator accounts

**********

``UpdateBehavior()``
----------------

Replaces the stream’s existing behavior with those defined in the ‘entity’. If certain aspects of the existing behavior are meant to remain, they must be included in entity.

An override list can be included in the ‘entity’ to cause
the addition, removal, or change to this list.

**Syntax**

::

    void UpdateBehavior(string tenantId, string namespaceId, string behaviorId, QiStreamBehavior entity);
    Task UpdateBehaviorAsync(string tenantId, string namespaceId, string behaviorId, QiStreamBehavior entity);

**Http**

::

    PUT Qi/{tenantId}/{namespaceId}/Behaviors/{behaviorId}	
**Parameters**

``string tenantID``
  The tenant identifier for the request
``string namespaceId``
  The namespace identifier for the request
``entity``
  The updated stream behavior

**Optional parameters**

  None
  
**Returns**
  An IEnumerable of all behavior objects

Security
  Allowed by administrator accounts

