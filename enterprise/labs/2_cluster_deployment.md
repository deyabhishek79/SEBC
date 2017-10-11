Cloudera Manager Configuration

```

[root@ip-172-31-41-199 ec2-user]# curl -u deyabhishek79:cloudera "http://52.90.50.48:7180/api/v2/cm/deployment"
{
  "timestamp" : "2017-10-11T17:44:10.200Z",
  "clusters" : [ {
    "name" : "deyabhishek79",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-18889174458b222d3ea0b61bb545528a",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0991900025324ef6e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "byugme1m9pxr4l0hwv3f62p5u"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-22da702c12c20f5132a8976a91f7b23a",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0744347f7c7c855ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ax4yfhclncnbsglojuo9i1qxx"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-4dc8a23e6b7a521e41bfb2ecd3e88564",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0afd1987da89ff6b6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a91yyyh29w0q1itneea8d4jq4"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-41-199.ec2.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "mariadb"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "mariadbuser"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "639631360"
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
        "name" : "oozie-OOZIE_SERVER-2f140eb864436f46955ae405f1672025",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ddo8ui1ene00vddim8l9f3hzs"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-41-199.ec2.internal"
        }, {
          "name" : "database_password",
          "value" : "mariadb"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "database_user",
          "value" : "mariadbuser"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-2f140eb864436f46955ae405f1672025"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-2f140eb864436f46955ae405f1672025",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9n1cac8bk6fwb5cocd4hl5brl"
          }, {
            "name" : "secret_key",
            "value" : "eS5Ah4gwkIqNi1IsRhPUpTqAEarYiW"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "4293706956"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
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
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "639631360"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "QgWarcqjJLUyM7TUX4m88wu0PMQa8x"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "KEV2ZufA08djgPz23h18asRmiTP4Lb"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "qxUz0orkEhO4iQyZtg4TvbItEr5Fj8"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-2f140eb864436f46955ae405f1672025",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-18889174458b222d3ea0b61bb545528a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0991900025324ef6e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7c2bcen48lo2fj9mrsdem0je1"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-22da702c12c20f5132a8976a91f7b23a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0744347f7c7c855ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4feykmafxp0b1quw333hufey1"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-4dc8a23e6b7a521e41bfb2ecd3e88564",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0afd1987da89ff6b6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3ioq6pm2wse7n0epi5i8zgfjd"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-a3d4d41681f14e240b0efe0361924c05",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-088921ebd5dd8aa67"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5f1bn4z34u2sglj22kp1okopp"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-2f140eb864436f46955ae405f1672025",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d4qg5giwftkclhjz65sxdccze"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-4dc8a23e6b7a521e41bfb2ecd3e88564",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0afd1987da89ff6b6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3gtpxe6qia8q3es8eb64toxkc"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-18889174458b222d3ea0b61bb545528a",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0991900025324ef6e"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn2"
          }, {
            "name" : "role_jceks_password",
            "value" : "87j0dbl8gggx0rucohlm4bvmg"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-22da702c12c20f5132a8976a91f7b23a",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0744347f7c7c855ea"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn1"
          }, {
            "name" : "role_jceks_password",
            "value" : "6hmgshvgfkljj1csl7pqwf8by"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-4dc8a23e6b7a521e41bfb2ecd3e88564",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0afd1987da89ff6b6"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn3"
          }, {
            "name" : "role_jceks_password",
            "value" : "3dw1lperrf1nol0cqnoh5z605"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-2f140eb864436f46955ae405f1672025",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "hdfs-ha-nameservice"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "hdfs-ha-nameservice"
          }, {
            "name" : "namenode_id",
            "value" : "46"
          }, {
            "name" : "role_jceks_password",
            "value" : "1j5bg4hzw6x3eamnqdgendyey"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-4dc8a23e6b7a521e41bfb2ecd3e88564",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0afd1987da89ff6b6"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "hdfs-ha-nameservice"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "hdfs-ha-nameservice"
          }, {
            "name" : "namenode_id",
            "value" : "61"
          }, {
            "name" : "role_jceks_password",
            "value" : "e66uqp4fsvbap04987qx4acdp"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1600"
          }, {
            "name" : "rm_io_weight",
            "value" : "800"
          }, {
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
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "1816"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "639631360"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4939"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "fKjN30Jv2PIeYH64PPvpKvda1DX9WI"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-2f140eb864436f46955ae405f1672025",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cn80w66lau1yta1s995xd6i5k"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-18889174458b222d3ea0b61bb545528a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0991900025324ef6e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4gxqtu94ffh9juycihwnkpbg9"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-22da702c12c20f5132a8976a91f7b23a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0744347f7c7c855ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9yowjprxj145ns5w89akkfwaf"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-4dc8a23e6b7a521e41bfb2ecd3e88564",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0afd1987da89ff6b6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "az5oyyhkqhhd5lejiddyri6eu"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-a3d4d41681f14e240b0efe0361924c05",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-088921ebd5dd8aa67"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5toresj4wedi0tbzkgcvninjo"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-2f140eb864436f46955ae405f1672025",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "53"
          }, {
            "name" : "role_jceks_password",
            "value" : "3lmjif0e4mbuti7n4axoc6zpe"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "639631360"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3433247539"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "577"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-41-199.ec2.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "mariadb"
        }, {
          "name" : "hive_metastore_database_user",
          "value" : "mariadbuser"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-18889174458b222d3ea0b61bb545528a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0991900025324ef6e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-22da702c12c20f5132a8976a91f7b23a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0744347f7c7c855ea"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-2f140eb864436f46955ae405f1672025",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-4dc8a23e6b7a521e41bfb2ecd3e88564",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0afd1987da89ff6b6"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-a3d4d41681f14e240b0efe0361924c05",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-088921ebd5dd8aa67"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-2f140eb864436f46955ae405f1672025",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b5vttwxooi1o99b56wpggnefr"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-2f140eb864436f46955ae405f1672025",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-03f4fa6c8c5c0a8a0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bpkcve49cpbrnertjsts6lowz"
          } ]
        }
      } ],
      "displayName" : "Hive"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-0744347f7c7c855ea",
    "ipAddress" : "172.31.33.224",
    "hostname" : "ip-172-31-33-224.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0991900025324ef6e",
    "ipAddress" : "172.31.37.254",
    "hostname" : "ip-172-31-37-254.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0afd1987da89ff6b6",
    "ipAddress" : "172.31.37.78",
    "hostname" : "ip-172-31-37-78.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-03f4fa6c8c5c0a8a0",
    "ipAddress" : "172.31.41.199",
    "hostname" : "ip-172-31-41-199.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-088921ebd5dd8aa67",
    "ipAddress" : "172.31.41.252",
    "hostname" : "ip-172-31-41-252.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-2f140eb864436f46955ae405f1672025",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3a294293f492a5b7491a9cfb77b281285670b09ec08971f96f752f23bcc8ee48",
    "pwSalt" : -2292092339866836528,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-2f140eb864436f46955ae405f1672025",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "d66ea062d3babe6090159e1b39d1b8249bdd0160c54e5de34c475303a6f977a4",
    "pwSalt" : -3694262134303229596,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-2f140eb864436f46955ae405f1672025",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "8a524801c7b046e58fadf015fbc8a3bdf348438279e2418e17313ad612f48923",
    "pwSalt" : 2178736547239737511,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-2f140eb864436f46955ae405f1672025",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "39f74fbae8a2eeaab096f4bd1a00df5bd67aa058995e04c00c27119dd08b94b7",
    "pwSalt" : -1202026559817097110,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "7c0633c59697471755d122f76ea22a7fcee1cbce67af540fe80f7f9e72a4a57f",
    "pwSalt" : -778453257054442816,
    "pwLogin" : true
  }, {
    "name" : "deyabhishek79",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "e81e1d6a7243dd893731cbcbd74e8a72068c00caa3a061f54d78c1c0500a8088",
    "pwSalt" : -3010689089403458360,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "e9f67552c6d38709dbc9d3b59eb034a8069dd4c3895ad10c7291fca3ea76de56",
    "pwSalt" : -2331966556211643001,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.9.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170627-1506",
    "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "639631360"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "639631360"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "831520768"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-41-199.ec2.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "mariadb"
        }, {
          "name" : "headlamp_database_user",
          "value" : "mariadbuser"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "639631360"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "639631360"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "831520768"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-2f140eb864436f46955ae405f1672025",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-03f4fa6c8c5c0a8a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8rjh1plj1tz1iyba464by53np"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-2f140eb864436f46955ae405f1672025",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-03f4fa6c8c5c0a8a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "d699qx5mgodnagzsi8d9n9c06"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-2f140eb864436f46955ae405f1672025",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-03f4fa6c8c5c0a8a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "44rj11ixxq22ameyr4o2u1u0y"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-2f140eb864436f46955ae405f1672025",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-03f4fa6c8c5c0a8a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "48km24i08jgzdqymorozlh053"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-2f140eb864436f46955ae405f1672025",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-03f4fa6c8c5c0a8a0"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9nw6dy24mmtoe1p2a8j25b7p7"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/21/2012 20:20"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}

```
