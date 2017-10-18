{
  "timestamp" : "2017-10-18T09:47:00.686Z",
  "clusters" : [ {
    "name" : "ibrahimsaf/SEBC",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "1447034880"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "1447034880"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3934152294"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "662"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-7-61.eu-central-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "azerty"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-40d7d26c7a2a203f8737bdbc6f1ed90e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0ba3a34f5e0203f6c"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-48efabdcd1219041d9b5bc1114adf15b",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-021d9bd82002bb94d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-a80c5e7255db726c5ddd31237391122c",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0210be72ac79e581c"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-b1e49664d7570c01a8e598ef148af130",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0c0342354ad6a38b2"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-c48708ab398fc8a2acdab5f004f6a929",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-05a47c8e06a1629d1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-48efabdcd1219041d9b5bc1114adf15b",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-021d9bd82002bb94d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5etsameordrv1qc1ot145efy7"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-48efabdcd1219041d9b5bc1114adf15b",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-021d9bd82002bb94d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bgshy9xmqulnzmpwu44p42n0g"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-40d7d26c7a2a203f8737bdbc6f1ed90e",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0ba3a34f5e0203f6c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "86hi6gie9dcp1f6qrk6qr657"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-48efabdcd1219041d9b5bc1114adf15b",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-021d9bd82002bb94d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "63b756dcb7s26ox93mktjeyh0"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-a80c5e7255db726c5ddd31237391122c",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0210be72ac79e581c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "18nl80z25q75kplpr1dk3wn8h"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-7-61.eu-central-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "azerty"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-48efabdcd1219041d9b5bc1114adf15b"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-a80c5e7255db726c5ddd31237391122c",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-0210be72ac79e581c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "75xpeyqz3md22ftzyg6aswrau"
          }, {
            "name" : "secret_key",
            "value" : "0UV5CWzYWMgyRSyRRFxF2juzwG5alX"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-7-61.eu-central-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "azerty"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-a80c5e7255db726c5ddd31237391122c",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-0210be72ac79e581c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e3t0qjdzbgcrcbkbect6j5t68"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "5745"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5745"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "4"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "hsb43K1M0WBWmVtXk0H4phnsVuGCuW"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-48efabdcd1219041d9b5bc1114adf15b",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-021d9bd82002bb94d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7wgb8x6e02djm1g9q7r2k3th2"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-40d7d26c7a2a203f8737bdbc6f1ed90e",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0ba3a34f5e0203f6c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "933lmj2ls1jbg5py30w0hjt35"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-b1e49664d7570c01a8e598ef148af130",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0c0342354ad6a38b2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "494lykwp9f028478u3nmktuhz"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-c48708ab398fc8a2acdab5f004f6a929",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-05a47c8e06a1629d1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7otf0ihffgvs7hme4s58msv3u"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-48efabdcd1219041d9b5bc1114adf15b",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-021d9bd82002bb94d"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "50"
          }, {
            "name" : "role_jceks_password",
            "value" : "9gjmzw86c78pj7rpm0vutfczw"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "10736126771"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "1073741824"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "1073741824"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "uu5javwvrNU1XPuhW0GFEpEhFEu21J"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "LqIUOrOJanQKlZ3LzHziwPyGlFCX49"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "P8Pc0AOGiZzmjiBp1lnsjyCZfkXoM3"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-48efabdcd1219041d9b5bc1114adf15b",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-021d9bd82002bb94d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-40d7d26c7a2a203f8737bdbc6f1ed90e",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0ba3a34f5e0203f6c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3z73r73x3kwf44vnlhq3xdps0"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-b1e49664d7570c01a8e598ef148af130",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0c0342354ad6a38b2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3gni9mvi618u37mxaj20wj922"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-c48708ab398fc8a2acdab5f004f6a929",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-05a47c8e06a1629d1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "epm4afquprsqyymidw1uou3by"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-48efabdcd1219041d9b5bc1114adf15b",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-021d9bd82002bb94d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4zrxqocpqwjjemal4fde7lj2j"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-a80c5e7255db726c5ddd31237391122c",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0210be72ac79e581c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9z1hgvcvdmwdbxjukz0ifkucg"
          } ]
        }
      }, {
        "name" : "hdfs-GATEWAY-a80c5e7255db726c5ddd31237391122c",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0210be72ac79e581c"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-40d7d26c7a2a203f8737bdbc6f1ed90e",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0ba3a34f5e0203f6c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6qsrntet3d4zhsv0jjlxncyxv"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-b1e49664d7570c01a8e598ef148af130",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0c0342354ad6a38b2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4r3u26suqyqab3xn2lzfsn3zs"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-c48708ab398fc8a2acdab5f004f6a929",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-05a47c8e06a1629d1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d4lk70qzf43chw24xfi6laa6q"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-48efabdcd1219041d9b5bc1114adf15b",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-021d9bd82002bb94d"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "52"
          }, {
            "name" : "role_jceks_password",
            "value" : "9615x9b1aot3er5dzngcnegzm"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-a80c5e7255db726c5ddd31237391122c",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0210be72ac79e581c"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "62"
          }, {
            "name" : "role_jceks_password",
            "value" : "a1yrxn3z5yjvvj552n7qf0kip"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-0ba3a34f5e0203f6c",
    "ipAddress" : "172.31.10.155",
    "hostname" : "ip-172-31-10-155.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "1"
      } ]
    }
  }, {
    "hostId" : "i-0c0342354ad6a38b2",
    "ipAddress" : "172.31.14.121",
    "hostname" : "ip-172-31-14-121.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "1"
      } ]
    }
  }, {
    "hostId" : "i-0210be72ac79e581c",
    "ipAddress" : "172.31.4.12",
    "hostname" : "ip-172-31-4-12.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "1"
      } ]
    }
  }, {
    "hostId" : "i-05a47c8e06a1629d1",
    "ipAddress" : "172.31.7.183",
    "hostname" : "ip-172-31-7-183.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "1"
      } ]
    }
  }, {
    "hostId" : "i-021d9bd82002bb94d",
    "ipAddress" : "172.31.7.61",
    "hostname" : "ip-172-31-7-61.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "1"
      } ]
    }
  } ],
  "users" : [ {
    "name" : "minotaur",
    "roles" : [ "ROLE_CLUSTER_ADMIN" ],
    "pwHash" : "cdeb7693e69bf2bd16c3f91d8e965c86e2fd85bb002668872365a82f4f3a88e3",
    "pwSalt" : 6001164202926613788,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1013",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-7-61.eu-central-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "amon"
        }, {
          "name" : "headlamp_database_password",
          "value" : "azerty"
        }, {
          "name" : "headlamp_database_user",
          "value" : "amon"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-a80c5e7255db726c5ddd31237391122c",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-0210be72ac79e581c"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1pns093zcvuyybr2not61x2gt"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-a80c5e7255db726c5ddd31237391122c",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-0210be72ac79e581c"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8budallznw0h5b5kemzri6xvo"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-a80c5e7255db726c5ddd31237391122c",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-0210be72ac79e581c"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "af3houz8ndwwhmguyixcip9cm"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-a80c5e7255db726c5ddd31237391122c",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-0210be72ac79e581c"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8ak81gw6l11llp75bleg1v1xu"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-a80c5e7255db726c5ddd31237391122c",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-0210be72ac79e581c"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "l854xlnx8gp9qx2livdhswch"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/24/2012 2:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://18.194.214.188/cdh5.8.3/"
    } ]
  }
}