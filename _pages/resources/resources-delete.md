---
title: Delete a resource
date: 2019-04-23 14:00:00 Z
layout: default
category: resources,delete
slug: resources-delete
permalink: /resources/delete
---

A Resource can be deleted subject to relevant permissions by sending a `DELETE` request to
 `/resources/<resourceId>.json`.

```
DELETE /resources/<resourceId>.json
```

### Possible responses

<table class="table-parameters">
<thead>
  <tr>
   <th>Code
   </th>
   <th>Description
   </th>
  </tr>
</thead>
<tbody>
  <tr>
   <td>200
   </td>
   <td>OK<br/>
    Resource deleted successfully.
   </td>
  </tr>
  <tr>
   <td>400
   </td>
   <td>Bad Request<br/>
    The resourceId supplied is not a valid UUID
   </td>
  </tr>
  <tr>
   <td>403
   </td>
   <td>Authentication Failure<br/>
    The user making the request is not authenticated
   </td>
  </tr>
  <tr>
   <td>404
   </td>
   <td>Not Found<br/>
    The resource either does not exist or the user does not have the permission to delete.
   </td>
  </tr>
  </tbody>
</table>