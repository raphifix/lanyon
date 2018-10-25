---
published: false
---
Adding users to groups in Redshift is done from the perspective of the group, not the user (as it took me longer than I'd like to admit to figure out).

`alter group group_name add user username;`