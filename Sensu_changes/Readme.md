Sensu has a check that calls "check-ceph-dash-graphite.py" in order to gather metrics about Ceph and relay them to Graphite.
On the Central Sensu server, copy the "check-ceph-dash-graphite.py" file in "/etc/sensu/plugins" and "check-ceph-dash.json" in "/etc/sensu/conf.d".
Also, add custom retention settings in carbon for the Ceph metrics bu editing "/etc/carbon/storage-schemas.conf" and adding:

[ceph]
pattern = ^ceph\.
retentions = 30s:1w,5m:1w,15m:180d

