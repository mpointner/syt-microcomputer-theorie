---
title: Update a group
date: 2019-04-23 14:00:00 Z
layout: default
category: groups,update
slug: groups-update
permalink: /groups/update
---

A Group can be updated by sending the `PUT` request to `/groups/<groupId>.json`.

```
PUT /groups/<groupId>.json
```
```json
{
  "name": "newgroupname",
  "groups_users": [{
    "user_id": "<userId_to_add>",
    "is_admin": false
  }, {
    "id": "<groupUserId_to_update_role>",
    "is_admin": true
  }, {
    "id": "<groupUserId_to_remove>",
    "delete": true
  }],
  "secrets":[{
    "resource_id":"<resource_shared_with_group",
    "user_id":"<new_userId>",
    "data":"-----BEGIN PGP MESSAGE-----"
  }]
}
```

When you update a group which has passwords shared with you also need to provide secrets for the new users. 
The dry-run gives information about this.

A dry run can also be performed before actually attempting to update a group:
```
PUT /groups/<groupId>/dry-run.json
```

This will check all the constraints and return a 200 OK response if the group can be updated safely.

### Possible responses

<table class="table-parameters">
    <thead>
        <tr>
            <th>Code</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>200</td>
            <td>OK<br/>
            The group was updated.</td>
        </tr>
        <tr>
            <td>400</td>
            <td>Bad Request<br/>
            Some of the data validation failed.</td>
        </tr>
        <tr>
            <td>403</td>
            <td>Authentication Failure<br/>
            The user making the request is not authenticated</td>
        </tr>
    </tbody>
</table>
