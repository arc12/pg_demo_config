# Basic Aggregated Usage
View the number of interactions ("counts") or the number of unique browser sessions.

For periods more than a few days, daily totals are shown, while for shorter periods, hourly totals appear. Note that only data for completed hours or days is counted, and that the data is updated a few minutes after the turn of the hour.

The unique session counts are somewhat problematical to interpret because of the way browsers treat session cookies. If the plaything is accessed in a plain browser window, the session id will persist over playthings and plaything views accessed in the same tab. For a plaything accessed via an iframe, the session id is scoped to a single plaything + view. The session id is really meant to allow grouping of interactions when analysing the pattern of user activity.